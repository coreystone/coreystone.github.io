---
title: "Awesome open-source privacy engineering"
date: "2024-12-24"
description: "A curation of tools, technologies, and frameworks open sourced for the advancement of the field."
tags:
  - FOSS
  - PrivacyEngineering
ShowToc: true
---

## Introduction
["Awesome" GitHub repos](https://github.com/pawelborkar/awesome-repos) are curated lists of information and resources relevant to a particular subeject area. There are a plethora of awesome privacy-related repos, and here are some standouts that influenced this list:

* [`awesome-privacy`](https://github.com/Lissy93/awesome-privacy)
* [`awesome-privacy-engineering`](https://github.com/mplspunk/awesome-privacy-engineering)
* [`AwesomePrivacyEngineering`](https://github.com/AbductiveReason/AwesomePrivacyEngineering)
* [`privacy-engineering-tools`](https://utrechtuniversity.github.io/privacy-engineering-tools/) 

However, I wasn't able to find a list of exclusively open-source, currently maintained tools and resources for privacy engineering, so I wanted to there to be one. 
This list focuses on currently updated, non-deprecated projects which are particularly interesting to me.


## Consent management platform (CMP)
#### `Klaro Privacy Manager`
> An open-source, privacy-friendly & compliant consent manager for your website.
* Author: [Klaro!](https://www.klaro.org/)
* Repo: [github.com/klaro-org/klaro-js](https://github.com/klaro-org/klaro-js)

A small, lightweight cookie consent solution based on JavaScript that provides notice and blocks third-party apps from executing without consent. 


#### `Osano Cookie Consent`
> A free solution to the EU, GDPR, and California Cookie Laws
* Author: [Osano](https://www.osano.com/cookieconsent)
* Repo: [github.com/osano/cookieconsent](https://github.com/osano/cookieconsent)

A similar lightweight JavaScript approach to a cookie consent preference center and notice mechanism.


#### `Open Cookie Database`
> The Open Cookie Database is an effort to describe and categorise all major cookies. All cookie descriptions are saved in a downloadable CSV file.
* Author: [Ketch](https://ketch.com/)
* Repo: [github.com/ketch-com/Open-Cookie-Database](https://github.com/ketch-com/Open-Cookie-Database)

A spreadsheet of common cookies and their associated domains, categories, and descriptions.


## Static code analysis
#### `Privado`
> Open Source Static Scanning tool to detect data flows in your code, find data security vulnerabilities & generate accurate Play Store Data Safety Report.
* Author: [Privado](https://docs.privado.ai/)
* Repo: [github.com/Privado-Inc/privado](https://github.com/Privado-Inc/privado)
* Watch: [Getting Started with Privacy Code Scanning](https://youtu.be/S-c3l8LGfD0)


## Data subject rights
#### `Fides`
> [A]n open-source privacy engineering platform for managing the fulfillment of data privacy requests in your runtime environment, and the enforcement of privacy regulations in your code.
* Author: [Ethyca](https://ethyca.com/docs)
* Repo: [github.com/ethyca/fides](https://github.com/ethyca/fides)

#### `Data Rights Protocol`
> The technical standard for exchanging data rights requests.
* Author: [Consumer Reports](https://datarightsprotocol.org/)
* Repo: [github.com/consumer-reports-innovation-lab/data-rights-protocol](https://github.com/consumer-reports-innovation-lab/data-rights-protocol)
* Watch: [PEPR '23 - Securing and Standardizing Data Rights Requests with a Data Rights Protocol](https://www.youtube.com/watch?v=CsXdr34ZotA&list=PLbRoZ5Rrl5le5MLOePeumxpQfUg2Gyfui&index=18)


#### `Ketch DSR Protocol`
* Author: [Ketch](https://ketch.com)
* Repo: ???
* Watch: [PEPR '24 - Building a Protocol to Improve DSR Flexibility and Integration](https://youtu.be/XotLV8JyLg0?list=PLbRoZ5Rrl5ldxIsGMFjwixoLxQ1iMq_BH)

This is Ketch's iteration of Consumer Reports's DRP. However, I was not able to find the source repo.

## Frameworks
#### `xCOMPASS (COMcast Privacy ASSistant)`
> [A] persona based privacy threat modeling solution called Models of Applied Privacy or MAP.
* *Previously called "Models of Applied Privacy" (MAP)*
* Author: [Comcast](https://github.com/Comcast/xCompass)
* Repo: [github.com/Comcast/xCOMPASS](https://github.com/Comcast/xCompass)


#### `Privacy Adversarial Framework` 
> The Privacy Adversarial Framework (PAF) is a knowledge base of privacy-focused adversarial tactics and techniques. PAF is heavily inspired by MITRE ATT&CK®.
* Author: [Meta Research](https://research.facebook.com/)
* Repo: [github.com/facebookresearch/privacy_adversarial_framework](https://github.com/facebookresearch/privacy_adversarial_framework)
* Watch: [PEPR '23 - How to Utilize Your Red Team for Privacy](https://www.youtube.com/watch?v=NEjPZrfK460&list=PLbRoZ5Rrl5le5MLOePeumxpQfUg2Gyfui&index=14)


#### `PANOPTIC Privacy Threat Model` 
> Publicly available privacy threat taxonomy for breaking down and describing privacy attacks against individuals and groups of individuals.
* *Pattern and Action Nomenclature Of Privacy Threats In Context*
* Author: [MITRE](https://www.mitre.org/)
* Repo: [ptmworkshop.gitlab.io/#/panoptic](https://ptmworkshop.gitlab.io/#/panoptic)

The authors of MITRE ATT&CK® in the cybersecurity space created a spiritual equivalent in the privacy space for "system and environmental privacy threat assessment, holistic privacy risk modeling, and privacy red teaming."


## Privacy enhancing technologies (PETs)
#### `PETAce`
> PETAce is a privacy-enhancing protocol framework based on state-of-the-art research results. It provides data processing methods such as secret sharing, homomorphic encryption, and oblivious transfer, and can perform collaborative computation and analysis of two-party data while preserving data privacy.
https://developers.tiktok.com/blog/enhance-privacy-using-PETAce
* *Privacy-Enhancing Technologies via Applied Cryptography Engineering*
* Author: [TikTok Privacy Innovation](https://privacyinnovation.io/)
* Repo: [github.com/tiktok-privacy-innovation/PETAce](https://github.com/tiktok-privacy-innovation/PETAce)
* Reading:
    1. [PETAce: Using Applied Cryptography to Enhance Privacy](https://developers.tiktok.com/blog/enhance-privacy-using-PETAce)

    2. [PETAce in Action: Enhancing privacy during Friends Matching in TikTok](https://developers.tiktok.com/blog/tiktok-practices-in-privacy-enhancing-technologies)


#### `PrivacyGo`
> PrivacyGo is the open-source synergistic fusion of various PETs, such as differential privacy, multi-party computation, homomorphic encryption, and artificial intelligence methods to enhance user privacy protection. PrivacyGo strives to carefully design approaches that harness the strengths of PETs while mitigating their individual limitations.
* Author: [TikTok Privacy Innovation](https://privacyinnovation.io/)
* Repo: [github.com/tiktok-privacy-innovation/PrivacyGo](https://github.com/tiktok-privacy-innovation/PrivacyGo)
* Watch: [PEPR '24 - Designing for User Privacy: Integrating Differential Privacy into Ad Measurement Systems in Practice](https://www.youtube.com/watch?v=OX4X78JRuf4&list=PLbRoZ5Rrl5ldxIsGMFjwixoLxQ1iMq_BH)
* Reading: 
    1. [PrivacyGo: TikTok’s initiative in synergistic privacy-enhancing technologies](https://developers.tiktok.com/blog/privacy-go)

#### `PipelineDP`
> PipelineDP is a Python framework for applying differentially private aggregations to large datasets using batch processing systems such as Apache Spark, Apache Beam, and more.
* Author: [OpenMined](https://openmined.org/) & [Google Research](https://research.google/)
* Repo: [github.com/OpenMined/PipelineD](https://github.com/OpenMined/PipelineDP)
* Watch: [PEPR '24 - Utility Analysis for Differentially-Private Pipelines](https://youtu.be/6y2kk6JPzZk?list=PLbRoZ5Rrl5ldxIsGMFjwixoLxQ1iMq_BH)


#### `Shadowgraphy`
> Shadowgraphy is an open-source data pseudonymization SDK.  Shadowgraphy provides secure APIs for seamless data pseudonymization, providing enterprises a consistent data protection service with industrial standards and best practices. By prioritizing ease of use and robustness, Shadowgraphy enables developers, even those without cryptography expertise, to integrate cryptographic pseudonymization techniques effectively, fostering a culture of privacy-aware development.
* Author: [TikTok Privacy Innovation](https://privacyinnovation.io/)
* Repo: [github.com/tiktok-privacy-innovation/Shadowgraphy](https://github.com/tiktok-privacy-innovation/Shadowgraphy)


#### `ManaTEE`
> [A]n open-source project for easily building and deploying data collaboration framework[s] to the cloud using trusted execution environments (TEEs).
* *Previously called PrivacyGo-DataCleanRoom*
* Author: [Confidential Computing Consortium (CCC)](https://confidentialcomputing.io/)
    * Previously: [TikTok Privacy Innovation](https://privacyinnovation.io/)
* Repo: [github.com/manatee-project/manatee](https://github.com/manatee-project/manatee)


#### `Private Computation Framework (PCF)`
> Private computation framework library allows developers to perform randomized controlled trials, without leaking information about who participated or what action an individual took. It uses secure multiparty computation to guarantee this privacy. It is suitable for conducting A/B testing, or measuring advertising lift and learning the aggregate.
* Author: [Meta Research](https://research.facebook.com/)
* Repo: [github.com/facebookresearch/FBPCF](https://github.com/facebookresearch/fbpcf)


#### `Private Computation Solutions (PCS)`
> FBPCS (Facebook Private Computation Solutions) leverages secure multi-party computation (MPC) to output aggregated data without making unencrypted, readable data available to the other party or any third parties. Facebook provides impression & opportunity data, and the advertiser provides conversion / outcome data.
* Author: [Meta Research](https://research.facebook.com/)
* Repo: [github.com/facebookresearch/FBPCS](https://github.com/facebookresearch/fbpcs)


#### `Private Join and Compute`
> This project contains an implementation of the "Private Join and Compute" functionality [which] allows two users, each holding an input file, to privately compute the sum of associated values for records that have common identifiers.
* Author: [Google Research](https://research.google/)
* Repo: [github.com/google/private-join-and-compute](https://github.com/Google/private-join-and-compute)


#### `PySyft`
> Perform data science on data that remains in someone else's server.
* Author: [OpenMined](https://openmined.org/)
* Repo: [github.com/OpenMined/PySyft](https://github.com/OpenMined/PySyft)
* Watch: [PEPR '24 - A New Model for International, Privacy-Preserving Data Science](https://www.youtube.com/watch?v=69_RGhIJwMU&list=PLbRoZ5Rrl5ldxIsGMFjwixoLxQ1iMq_BH&index=11)

{{< figure align=left src="/images/pysyft-data-flow.png" >}}
*via xD.gov PEPR '24 presentation*