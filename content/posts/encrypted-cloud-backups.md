---
title: "Encrypted cloud backups with Cryptomator"
date: "2021-12-18"
description: "I heard you like encryption, so I encrypted your encrypted backups."
tags:
  - FOSS
  - privacy
  - security
ShowToc: true
---

## Introduction
I've recently taken it upon myself to be in charge of backing up my family's digital files and photos. 
It's not the most exciting thing, but God knows it won't get done otherwise and it is extremely important.

I'm following the golden [3-2-1 backup rule](https://www.seagate.com/blog/what-is-a-3-2-1-backup-strategy/), to keep copies of our data in three separate locations, 
in two different types of storage, and one offline backup. An example approach would be a copy of data in the cloud, on a cold (offline) hard drive, and another copy on a phone. 
I already have copies on a hard disk and other devices covered, so that just leaves me with picking a cloud storage provider to go with.

Popular options like Apple iCloud and Google Drive are appealing because they offer a lot of storage space at a reasonable price, and make it easy to access files across devices.
And those names alone carry a lot of weight and security in their own right.

However, there are some serious privacy concerns with these services. Both Apple and Google scan the files uploaded to their cloud for various service reasons, such as improving user experience and app performance, but this ultimately means that they are analyzing the files that you upload. This can be worrying because it raises questions about who can see our data and how it might be used. Especially in light of recent events after Apple has proposed a [new system to scan images](https://www.bbc.co.uk/news/technology-58145943) for child abuse material ("CSAM").


## Encrypted cloud storage
That's why I'm considering cloud providers that offer [zero-knowledge encryption](https://en.wikipedia.org/wiki/Zero-knowledge_service). With zero-knowledge encryption, even the service provider can't access my files because they don't have the keys to decrypt them. This means my data is much more secure and private. Only I can access my files, and I can be confident that no one else can see them.

We want to encrypt our files because it adds an extra layer of security. If someone were to gain unauthorized access to the cloud service, they wouldn't be able to read my files without the encryption key. This is especially important for sensitive information, like personal documents or financial records.

There are fortuantely a plethora of such services now available to consumers, so do your research and pick the service that seems right for you in terms of pricing.
For the purpose of this article, I will be using [MEGA](https://mega.nz/) (formerly known as [Mega Upload](https://en.wikipedia.org/wiki/Megaupload), which is a different rabbit hole I recommend when you have the time).

{{< figure align=left src="/images/zero-knowledge.png" >}}
*via [Tresorit](https://tresorit.com/features/zero-knowledge-encryption)*


## File encryption
To go the extra mile, you can also consider encrypting your files *before* uploading them to any third-party storage service.
This may sound overkill, but it can also give you the peace of mind knowing your files are safe even if the cloud provider
or their keys become compromised. This means that only you can truly see your files. This also means that you have the burden
of safely storing and protecting your encryption keys at the risk of losing all of your data.

There are tons of popular encryption programs, but for this article I will be using [Cryptomator](https://itsfoss.com/cryptomator/).

{{< figure align=left src="/images/cryptomator-logo.png" >}}

## Things you'll need
Note: For this article, I will be using Windows. However, the steps are ultimately the same across any OS.
* [Cryptomator](https://cryptomator.org/) for encrypting files before uploading them to the cloud
* A cloud storage provider, preferrably with a desktop app like [MEGAsync](https://mega.nz/desktop)
* If you are backing up files larger than 4GB, [Dokany](https://github.com/dokan-dev/dokany/)

## Create an encrypted vault
We need to create a Cryptomator "vault" to store and encrypt our files. Vaults are actually Windows [virtual drives](https://medium.com/r?url=https%A%2F%2Fcomputer.howstuffworks.com%2Fvirtual-hard-drive1.htm)
that Cryptomator will mount whenever you unlock them and will persist in your drive's storage when they are locked.

Before we do that though, we need to decide what volume type we're going to be using: [WebDAV or Dokany](https://medium.com/r/?url=https%3A%2F%2Fcommunity.cryptomator.org%2Ft%2Fwebdav-vs-dokany-performance-comparison-when-using-remote-offsite-vault%2F2883%2F2). 
Unless you're a "power user",  [according to a Cryptomator dev](https://medium.com/r/?url=https%3A%2F%2Fcommunity.cryptomator.org%2Ft%2Fwhat-is-dokan-file-system-driver%2F3369), you really shouldn't worry about the 
difference between the two and should probably go with Dokany. In my case, I actually needed Dokany 
to transfer files larger than 4GB, which otherwise resulted in errors when I tried with WebDAV. 
Download and install the [newest release](https://medium.com/r/?url=https%3A%2F%2Fgithub.com%2Fdokan-dev%2Fdokany%2Freleases) of Dokany from GitHub and then return to Cryptomator.

{{< figure align=left src="/images/cryptomator-dokany.png" >}}

In Cryptomator, click on the "Preferences" gear icon in the top right and then go to "Virtual Drive".
WebDAV should be selected by default. If you need to use Dokany, make sure you have installed the
newest release already and then select it from the drop down menu (there are only two options).

{{< figure align=left src="/images/cryptomator-main.png" >}}


Start by clicking "Add Vault" and name it. You'll then be prompted to create a password and optionally 
receive a recovery key for said vault. A recovery key is the only way to recover a vault if you lose
this password. It is highly recommended to create a recovery key and store it somewhere safely, such
as a password manager- preferably one that has [zero-knowledge encryption](https://medium.com/r/?url=https%3A%2F%2Fcloudstorageinfo.org%2Fzero-knowledge-encryption-explained), in the spirit of our backup.

{{< figure align=left src="/images/cryptomator-create-vault.png" >}}


Now we're going to store this vault within the MEGA synced folder we created earlier.
Press the "Custom Location" button and then "Choose" and select the synced folder.
Either copy and paste the path of the MEGA folder or navigate to it in your file browser.
I placed my synced folder in my C: drive, so I will navigate there and then select it.

{{< figure align=left src="/images/cryptomator-vault-path.png" >}}


Now that our vault is prepared and placed in the synced folder, we can begin to transfer files to it. 
First ensure that your vault is unlocked and then start transferring your files to it in File Explorer.
Transfer your files directly to the vault and not to the synced folder, or else anything you transfer 
will be unencrypted. Your vault will appear as a virtual drive in File Explorer with the vault name and
an assigned letter- `vault_name (X:)`- this is where I dragged and dropped all of my files to.

You can check that you are doing things right by going to the synced folder and finding the now 
encrypted contents that you transferred. In my synced folder, I found my files inside a hierarchy of
arbitrary sub-folders. Your files' names will be obfuscated by Cryptomator and all files will have
the type `Cryptomator Encrypted Data (.c9r)`.

This is key: even though we can supposedly trust MEGA and its zero-knowledge encryption,
we really don't even need to now that our backup is entirely encrypted. This just adds another
layer of security on top of MEGA's [User Controlled Encryption](https://medium.com/r/?url=https%3A%2F%2Fmega.io%2Fsecurity) and in theory removes the need to trust
MEGA in the first place. This revelation goes for any cloud storage provider and turns less private
alternatives like Google Drive and iCloud into more appealing choices based on their superior pricing models.

{{< figure align=left src="/images/mega-uploading.png" >}}

You can check the progress of your sync by running the MEGAsync application,
which may already be hidden in the tray on the right of your taskbar. 
MEGA will try to sync multiple files simultaneously, but I noticed that
larger files like videos would only be uploaded one at a time.

## Uploading to the cloud
Now that the files are encrypted (as a .c9r), simply upload them to the cloud like you would any other file. I recommend a cloud provider has desktop sync app to make this 
a continuous process that happens behind the scenes, so you don't have to worry about anything or risk forgetting to back something up.

## Accessing files in the cloud
Once the files are in the cloud, you can simply decrypt them with the key that you set earlier and be assured that only you have been able to read your data.