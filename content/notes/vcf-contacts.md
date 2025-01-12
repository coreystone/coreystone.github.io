---
title: "An exercise in triviality: .vcf files and vCards"
date: "2025-01-11"
ShowToc: true
ShowReadingTime: true
description: " "
---

I'm doing some digital decluttering and turning my focus to the Contacts on my phone. In my case, contacts have always been one of those things that you set once and forget - 
so I've been amassing them ever since without looking back or keeping things up-to-date. It's a mess. There is a worrying number of contacts where I can't remember 
who the person is- either because I didn't provide enough information, or I just can't remember the person for the life of me- or I no longer need the contact in my phone.
I also figure that the more contacts I have in my phone, the more likely it is that 
I'll accidentally buttdial someone that I don't want to talk to or don't remember - so I'd like to avoid that.

For years, I was not doing my future self any favors by saving contacts on a first name only basis; if I'm lucky, I saved the initial of the person's last name. Wow that was dumb.

{{< figure align=left src="/images/random-contact.jpeg" >}}
*A totally real contact I found.*

Also, I realized that I haven't been taking advantage of any other contact fields, so I'd like to start enriching each contact where possible with things like email address, physical address, any extra phone numbers, and any other notes that might be useful in the future.
You never know when you'll need to remember someone's birthday, or their address for when they invite you to the birthday party that you forgot about.

{{< figure align=left src="/images/gw-contact.jpeg" >}}
*I wonder what George Washington's vCard would have looked like...*

To start, I could have just manually sorted through and edited each contact directly within the app on my phone. 
For reference, I am using [Fossify Contacts](https://github.com/FossifyOrg/Contacts) for Android, which is a FOSS contacts app. It's really boring, simple, and therefore perfect for my needs. 
But doing all that work on my phone sounds slow, tedious, and annoying to type everything out, so I wanted to try to see if there's a better way to do this. 

On Android it's super easy to export a contact list as a [.vcf file](https://en.wikipedia.org/wiki/VCard), which stands for a "virtual contact file".
Also known as a "vCard"... though I think (hope) that term is losing its popularity for reasons. 

After a few minutes of research, I realized this topic to be even more niche than I had thought,
as there really aren't many tools out there that don't look super sketchy or filled with ads. 

I did find a FOSS [vCardEditor](https://github.com/abdelkader/vCardEditor) by @[abdelkader](https://github.com/abdelkader/) on GitHub, which checks most boxes *except* it doesn't
support birthdays, which is something I really wanted. At this point, it seemed like a have a cake and eat it too kind of situation. 

{{< figure align=left src="/images/vcard-editor.png" >}}
*via [github.com/abdelkader/vCardEditor](https://github.com/abdelkader/vCardEditor)*

Ultimately, I decided to just do this in [VSCodium](https://vscodium.com/), as practically any text editor is able to work with .vcfs. 
Of course, I backed up my contacts first before doing anything-- I wouldn't want to... *lose my vCards*. Thank you, I'll be here all week.

These things are super simple, albeit a bit messy to look at. Here is an example vCard:
```
BEGIN:VCARD
VERSION:4.0
PRODID:-//ez-vCard 0.11.3//EN
FN:SpongeBob SquarePants
N:SquarePants;SpongeBob;;;
EMAIL:spongebob@spongebob.com
TEL;TYPE=cell:+1-555-000-0001
BDAY:1999-05-01
ADR;TYPE=home:;;124 Conch Street;Bikini Bottom;Ocean;12345;USA
END:VCARD
```

There's gotta be a better way to edit these, right? This use case seems perfect for spreadsheets. Again, I can find lots of older threads like [this one](https://answers.microsoft.com/en-us/outlook_com/forum/all/converting-from-vcf-to-csv/62bb1fa2-4e94-4185-a944-c163f477528b) where someone is trying to import export their Windows Phone contacts to a .csv. It seems that
some workarounds existed in Windows 7, and there's lots of online tools that let you convert your .vcf files directly, but there is no way I'm uploading my personal contacts into a random website.

Saying this is a niche topic in 2025 seems like an understatement-- it feels like I'm the only person in the world dealing with this right now. It's difficult to find a programmatic solution to do this that *also* supports more personal fields that I'm looking for, like `BDAY`. The [vCard Wikipedia page](https://en.wikipedia.org/wiki/VCard#Properties) shows all the fields supported by each version number.
This [vcard2csv repo](https://github.com/nbeaver/vcard2csv) supports the basics. [vcard4](https://github.com/kelseykm/vcard4) is actually *too perfect* for such a niche topic, so hats off to this developer.

So I ended up just going through and editing everything in VSCode anyways. I have an itch to come up with a solution for vCard 4.0, but I know I'll probably only ever use it once and then never need it again. Maybe when I have some more free time.

Now I'm really curious how many other people have found themselves in the same boat as me. I'm sure there's a handful of people trying to export contacts from an old phone or do some digital spring cleaning like I did. These vCards are also the basis for Outlook and iCloud contacts as well, so everyone is using them whether they realize it or not.

In the future, I'm going to add more information to a contact *as I create it* to avoid the need to do this again.
After reading through all the vCard property types, I feel an overwhelming urge to to spend much more time on this than I should by enriching more of my contacts with some of these properties. I think doing this for professional contacts is a good start- or at least that's how my will trick me into getting started in the first place.

| Name                          | Description                                                                                                           | Example                                                                                                           |
|-------------------------------|-----------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| `BDAY`                        | Date of birth of the individual associated with the vCard.                                                          | `BDAY:19700310`                                                                                                 |
| `CATEGORIES`                  | A list of "tags" that can be used to describe the object represented by this vCard.                                 | `CATEGORIES:swimmer,biker`                                                                                      |
| `GENDER`                      | Defines the person's gender.                                                                                         | `GENDER:F`                                                                                                      |
| `KEY`                         | The public encryption key associated with the vCard object. It may point to an external URL, may be plain text, or may be embedded in the vCard as a Base64 encoded block of text. | `KEY;MEDIATYPE=application/pgp-keys:http://example.com/key.pgp` or `KEY:data:application/pgp-keys;base64,[base64-data]` |
| `LANG`                        | Defines a language that the person speaks.                                                                           | `LANG:fr-CA`                                                                                                   |
| `ORG`                         | The name and optionally the unit(s) of the organization associated with the vCard object. This property is based on the X.520 Organization Name attribute and the X.520 Organization Unit attribute. | `ORG:Google;GMail Team;Spam Detection Squad`                                                                    |
| `REV`                         | A timestamp for the last time the vCard was updated.                                                                | `REV:20121201T134211Z`                                                                                          |
| `TITLE`                       | Specifies the job title, functional position or function of the individual associated with the vCard object within an organization. | `TITLE:V.P. Research and Development`                                                                           |
| `TZ`                          | The time zone of the vCard object.                                                                                  | `TZ:America/New_York`                                                                                     |

And this, ladies and gentlemen, has been an exercise in taking a trivial task then putting way more time and thought into it than I should in order to shirk more important, real-life responsibilities-- a microcosm of my life.