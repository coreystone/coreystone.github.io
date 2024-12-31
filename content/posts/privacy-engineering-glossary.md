---
title: "A privacy engineering glossary"
date: "2024-12-31"
description: "Defining and exploring privacy computation concepts and technologies."
tags:
  - PrivacyEngineering
ShowToc: true
weight: 2
---

## A
#### `Aggregation`
A statistical method to combine a collection of raw data and output it as a total or summary of that data. 
Useful for analytics and research. Offers a modicum of privacy protection, but still susceptible to re-identification attacks.
* Read more: [What Is Data Aggregation?](https://coefficient.io/data-aggregation)
* Related: [*Re-identification*](#re-identification)


#### `Algorithmic fairness`
The notion that algorithms should make decisions without "bias", ensuring equitable treatment across different demographic groups in a dataset.
* Read more: [What is Algorithm Fairness?](https://towardsdatascience.com/what-is-algorithm-fairness-3182e161cf9f)


#### `Anonymization`
The "process by which personal data is altered in such a way that a data subject can no longer be identified directly or indirectly,
either by the data controller alone or in collaboration with any other party" ([ISO 25237:2017](https://www.iso.org/standard/63553.html)). 
* Data is erased or overwritten absolutely in an attempt to delink it from an individual.
* Related: [*De-identification*](#data-classification), [*Pseudonymization*](#pseudonymization-tokenization)


#### `Authorization (AuthZ)`
A set of permissions for an authenticated user.
* Mechanisms include: Role-based access control (RBAC), Policy-based access control (PBAC)
* Read more: [Authn vs. authz: How are they different?](https://www.cloudflare.com/learning/access-management/authn-vs-authz/)
* Related: [*Authentication (AuthN)*](#authenticaton-authn)

{{< figure align=left src="/images/authn-vs-authz.png" >}}
*via [Heimdal Security](https://heimdalsecurity.com/blog/authentication-vs-authorization/)*


#### `Authenticaton (AuthN)`
Ensuring a person (or system) is who they claim they are by verifying their identity.
* Mechanisms include: Asymmetric/public-key cryptography (certificate exchange), username/password login, biometrics, et. al
* Related: [*Authorization (AuthZ)*](#authorization-authz)


#### `Availability`
* Data is readily served upon request without delay or downtime.
* Read more: [What is the CIA Triad and Why is it important?](https://www.fortinet.com/resources/cyberglossary/cia-triad)
* Related: [*Confidentiality*](#confidentiality), [*Integrity*](#integrity), [*CIA triad*](#cia-triad)


## B
#### `Background knowledge attack`
A type of attack against [k-anonymity](#k-anonymity) where an adversary uses external information to infer sensitive data about individuals from anonymized datasets.
* Read more:
  * [Background knowledge attacks in privacy-preserving data publishing models](https://www.sciencedirect.com/science/article/abs/pii/S0167404822002681?via%3Dihub)
  * [ℓ-Diversity: Privacy Beyond k-Anonymity](https://www.cs.rochester.edu/u/muthuv/ldiversity-TKDD.pdf)
* Related: [*K-anonymity*](#k-anonymity), [*Re-identification*](#re-identification)

{{< figure align=left src="/images/bg-knowledge-attack.png" >}}
*via [CS 295 Data privacy and confidentiality](https://www.slideserve.com/paytah/l-diversity-privacy-beyond-k-anonymity)*


## C
#### `CIA triad`
Confidentiality, Integrity, Availability. An archetype of cybersecurity. 
* Read more: [What is the CIA Triad and Why is it important?](https://www.fortinet.com/resources/cyberglossary/cia-triad)
* Related: [*Confidentiality*](#confidentiality), [*Integrity*](#integrity), [*Availability*](#availability)

{{< figure align=left src="/images/cia-triad.png" >}}
*via [thingscoupledo.com](https://thingscouplesdo.com/what-is-cia-triad-and-how-does-it-work/)*


#### `Confidentiality`
Data is protected as to prevent any unauthorized access, "whether intentional or accidental".
* Read more: [What is the CIA Triad and Why is it important?](https://www.fortinet.com/resources/cyberglossary/cia-triad)
* Related: [*CIA triad*](#cia-triad), [*Integrity*](#integrity), [*Availability*](#availability)


#### `Consent management platform (CMP)`
A data governance tool to obtain, record, map, and manage user consent for data collection and processing in compliance with privacy regulations.
* Read more: [What is Consent Management Platform (CMP) & Why Do You Need It?](https://securiti.ai/what-is-consent-management-platform-cmp/)


## D
#### `Data classification`
A hierarchy or class system used to assign risk or sensitivity levels to data, where higher levels indicate higher risk or sensitivity (and potentially prescribe stricter controls). The most popular example is the [US government's information classification system](https://en.wikipedia.org/wiki/Classified_information_in_the_United_States), which includes "Top Secret" and "Classified".
* Read more: 
  * [How Are US Government Documents Classified?](https://www.history.com/news/top-secret-classification-documents)
  * [Data Classification](https://www.imperva.com/learn/data-security/data-classification/)


#### `Data lineage`
A complete history of the lifecycle of a data point, from beginning to end. This includes all transformations, movement, and other operations performed on the data.
> [Lineage (n)](https://www.wordnik.com/words/lineage): Descent in a line from a common progenitor
* Read more: 
  * [What is Data Lineage and Data Provenance? Quick Overview](https://www.graphable.ai/blog/what-is-data-lineage-data-provenance/)
  * [Data Lineage tools and its Best Practice | Complete Guide](https://www.xenonstack.com/blog/data-lineage-tools)
* Related: [*Data provenance*](#data-provenance)

{{< figure align=left src="/images/data-lineage.png" >}}
*via [xenonstack.com](https://www.xenonstack.com/blog/data-lineage-tools)*


#### `Data minimization`
The principle of limiting data collection to only what is necessary for a specific purpose, reducing privacy "attack surface".
* Read more: [Data minimization: An increasingly global concept](https://iapp.org/news/a/data-minimization-an-increasingly-global-concept/)


#### `Data provenance`
A high-level overview of "where the data comes from."
> [Provenance (n)](https://www.wordnik.com/words/provenance): Place of origin; derivation. 
* Read more: 
  * [What is Data Provenance?](https://www.ibm.com/think/topics/data-provenance)
  * [What is Data Lineage and Data Provenance? Quick Overview](https://www.graphable.ai/blog/what-is-data-lineage-data-provenance/)
* Related: [*Data lineage*](#data-lineage)


#### `Data quality`
The relative accuracy, completeness, reliability, and relevance of data which is important for compliance and relevant analytical efforts.
It is important to avoid storing "stale" data.
* Read more: [Understanding Data Quality](https://www.dataversity.net/understanding-data-quality/)

{{< figure align=left src="/images/data-quality.png" >}}
*via [gaine.com](https://gaine.com/blog/mdm/data-quality-checks-your-key-to-reliable-and-accurate-information/)*


#### `Data tagging`
The process of labeling data with metadata to enhance its organization, retrieval, and compliance with privacy regulations.
* Distinct, machine-readable inputs used to filter data across systems
* Usually represented as or similar to a regular expression
* Read more: [Data Tagging: What You Need to Know](https://www.dataversity.net/data-tagging-what-you-need-to-know/)


#### `De-identification`
The general process of removing or altering personal information from a dataset to prevent the identification of individuals, while still allowing for useful data analysis.
* Read more: [De-identification: A Primer](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html)
* Related: [*Anonymization*](#anonymization)


#### `Delta (δ) presence`
A mathematical concept that refers to the ability to determine whether a specific individual is present in a dataset based on the changes in data over time.
* "This is slightly different than re-identification risk in that the goal is not to find which exact record corresponds which individual, only to know whether an individual is part of the dataset."
* Read more: [About δ-presence](https://cloud.google.com/sensitive-data-protection/docs/concepts-risk-analysis#about-delta-presence)


#### `Deterministic algorithm`
An algorithm that "always returns the same result given the same input parameters in the same state" of a dataset. 
* Read more: 
  * [Deterministic function in MySQL](https://stackoverflow.com/questions/7946553/deterministic-function-in-mysql)
  * [Difference between Deterministic and Non-deterministic Algorithms](https://www.tutorialspoint.com/difference-between-deterministic-and-non-deterministic-algorithms)
* Related: [*Non-deterministic algorithm*](#non-deterministic-algorithm)


#### `Differential privacy`
A privacy-preserving mathematical framework to maximize the accuracy of queries from statistical databases while minimizing the chances of identifying individual entries in the dataset by introducing **noise**.
* Read: [A Survey of Differential Privacy Frameworks](https://blog.openmined.org/a-survey-of-differential-privacy-frameworks/)
* Watch: [What is Differential Privacy?](https://www.youtube.com/watch?v=-JRURYTfBXQ)
* Related: [*Privacy-enhancing technology (PET)*](#privacy-enhancing-technology-pet)

{{< figure align=left src="/images/differential-privacy-models.png" >}}
*via [OpenMined](https://blog.openmined.org/a-survey-of-differential-privacy-frameworks/)*


#### `Downcoding attack`
An attack against "quasi-identifier-based deidentification techniques (QI-deidentification)[,] including k-anonymity, l-diversity, and t-closeness."
* Read more: 
  * [New kind of attack called 'downcoding' demonstrates flaws in anonymizing data](https://techxplore.com/news/2022-10-kind-downcoding-flaws-anonymizing.html)
  * [Attacks on Deidentificaton's Defenses](https://www.semanticscholar.org/paper/Attacks-on-Deidentification's-Defenses-Cohen/784de911b3cc582776a0dc26501a0e440ba11851)
* Watch: [USENIX Security '22 - Attacks on Deidentification's Defenses](https://www.youtube.com/watch?v=lB516bLBO7s)


## F
#### `Federated learning`
A decentralized machine learning approach that enables disparate data sources (nodes) to collaboratively train a central model,
without having training data ever leave any data source or be sent to the central (federated) server.

* Read more:
  * [Federated Learning](https://www.techopedia.com/definition/federated-learning)
  * [What Is Federated Learning?](https://blogs.nvidia.com/blog/what-is-federated-learning/)
  * [Federated Learning: Collaborative Machine Learning without Centralized Training Data](https://research.google/blog/federated-learning-collaborative-machine-learning-without-centralized-training-data/)
* Related: [*Privacy-enhancing technology (PET)*](#privacy-enhancing-technology-pet)

{{< figure align=left src="/images/federated-learning.png" >}}
*via [NVIDIA](https://blogs.nvidia.com/blog/what-is-federated-learning/)*

## H
#### `Homogeneity attack`
An attack on a k-anonymous dataset where the  attacker exploits "groups that leak information due to lack of diversity in the sensitive attribute." To address this, 
a sanitized table should be “diverse”, where "all tuples that share the same values of their quasi-identifiers should have diverse values for their sensitive attributes."
* Read more: [ℓ-Diversity: Privacy Beyond k-Anonymity](https://www.cs.rochester.edu/u/muthuv/ldiversity-TKDD.pdf)
* Related: [*K-anonymity*](#k-anonymity), [*Background knowledge attack*](#background-knowledge-attack)

{{< figure align=left src="/images/homogeneity-attack.png" >}}
*via [CS 295 Data privacy and confidentiality](https://www.slideserve.com/paytah/l-diversity-privacy-beyond-k-anonymity)*


#### `Homomorphic encryption`
A "method to encrypt data and perform operations on it" without having to decrypt the data. Particular use cases include financial, health, and other environments with highly sensitive data.
* There are several [types of homomorphic encryption](https://digitalprivacy.ieee.org/publications/topics/types-of-homomorphic-encryption)
* A popular example is the asymetric algorithm [RSA](https://www.splunk.com/en_us/blog/learn/rsa-algorithm-cryptography.html), which is *partially homomorphic*
* Read more: 
  * [What is Homomorphic Encryption?](https://blog.openmined.org/what-is-homomorphic-encryption/)
  * [Homomorphic Encryption: How It Works](https://www.splunk.com/en_us/blog/learn/homomorphic-encryption.html)
* Related: [*Privacy-enhancing technology (PET)*](#privacy-enhancing-technology-pet)

{{< figure align=left src="/images/homomorphic-encryption.png" >}}
*via [OpenMined](https://heimdalsecurity.com/blog/authentication-vs-authorization/)*


## I
#### `Insecure direct object reference (IDOR)`
A "vulnerability that arises when attackers can access or modify objects by manipulating identifiers used in a web application's URLs or parameters." Poor access controls fail to verify if a user is authorized to access data (such as that of another user).
* Read more: [Insecure Direct Object Reference Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Insecure_Direct_Object_Reference_Prevention_Cheat_Sheet.html)
* Related: [*CIA triad*](#cia-triad), [*Integrity*](#integrity), [*Availability*](#availability)

{{< figure align=left src="/images/idor.png" >}}
*via [@Steiner254 on Medium](https://medium.com/@Steiner254/insecure-direct-object-references-idor-16bf0b981b90)*


#### `Integrity`
Data is free from corruption, manipulation, or other unknown modifications. Data is "authentic, accurate, and reliable".
* Read more: [What is the CIA Triad and Why is it important?](https://www.fortinet.com/resources/cyberglossary/cia-triad)
* Related: [*Availability*](#availability), [*CIA triad*](#cia-triad), [*Confidentiality*](#confidentiality)


## K
#### `K-anonymity`
"A property of anonymized data" with "scientific guarantees that the individuals who are the subjects of the data cannot be re-identified while the data remain practically useful."
* Read more: 
  * [k-Anonymity: A Model for Protecting Privacy](https://epic.org/wp-content/uploads/privacy/reidentification/Sweeney_Article.pdf?utm_source=Data+Protocol+Docs&utm_medium=referral&utm_campaign=Data+Sharing:+A+Guide+to+Anonymization&utm_id=DP)
  * [About k-anonymity](https://cloud.google.com/sensitive-data-protection/docs/concepts-risk-analysis#about-k-anonymity)
  * [Data Sharing: A Guide to Anonymization](https://docs.dataprotocol.com/guides/data-sharing-a-guide-to-anonymization)
* Related: [*Privacy-enhancing technology (PET)*](#privacy-enhancing-technology-pet)


#### `K-map`
A similar approach to k-anonymity, "except that it assumes that the attacker most likely doesn't know who is in the dataset."
* Read more: 
  * [Computing k-map for a dataset](https://cloud.google.com/sensitive-data-protection/docs/compute-k-map)
  * [k-map, the weird cousin of k-anonymity](https://desfontain.es/blog/k-map.html)
  * [About k-map](https://cloud.google.com/sensitive-data-protection/docs/concepts-risk-analysis#about-k-map)
* Related: [*Privacy-enhancing technology (PET)*](#privacy-enhancing-technology-pet)


## L
#### `ℓ-diversity`
An attempt to address k-anonymity attacks (such as homogeneity and background knowledge attacks), which "attempts to measure how much an attacker can learn about people in terms of k-anonymity and equivalence classes". 
* Read more: 
  * [About l-diversity](https://cloud.google.com/sensitive-data-protection/docs/concepts-risk-analysis#about-l-diversity)
  * [ℓ-Diversity: Privacy Beyond k-Anonymity](https://www.cs.cornell.edu/johannes/papers/2006/2006-icde-publishing.pdf?utm_source=Data+Protocol+Docs&utm_medium=referral&utm_campaign=Data+Sharing:+A+Guide+to+Anonymization&utm_id=DP)
* Related: [*Privacy-enhancing technology (PET)*](#privacy-enhancing-technology-pet)

{{< figure align=left src="/images/l-diversity.png" >}}
*via [Kato Mivule](https://www.researchgate.net/figure/An-illustration-of-l-Diversity-for-sensitive-attribute-values_fig3_266740295)*


## N
#### `Non-deterministic algorithm`
An algorithm that "does not necessarily always return the same result given the same input parameters in the same state" of a dataset. [(Stack Overflow)](https://stackoverflow.com/questions/7946553/deterministic-function-in-mysql)
* Read more: [Difference between Deterministic and Non-deterministic Algorithms](https://www.tutorialspoint.com/difference-between-deterministic-and-non-deterministic-algorithms)
* Related: [*Deterministic algorithm*](#deterministic-algorithm)


## P
#### `Privacy by design`
A collection of data privacy principles proposed by Dr. Ann Cavoukian to take a "proactive approach to privacy that emphasises the need to incorporate data protection practices into projects and decisions at the outset, rather than as an afterthought."
* Read more: [Privacy by Design The 7 Foundational Principles](https://privacy.ucsc.edu/resources/privacy-by-design---foundational-principles.pdf)
* Related: [*Software development lifecycle*](#software-development-lifecycle-sdlc)

{{< figure align=left src="/images/pbd-infographic.png" >}}
*via [CookieYes](https://www.cookieyes.com/blog/privacy-by-design/)*


#### `Privacy-enhancing technology (PET)`
An assortment of tools that that enable businesses to comply with privacy regulations while preserving the individual privacy and utility of their data sets, for purposes such as analytics, development,  sharing, etc.
* Popular PETs: Homomorphic encryption, de-identification (k-anonymity), differential privacy, federated learning, secure multiparty computation, private set intersection, synthetic data, zero knowledge proofs, trusted execution environments
* Read more: 
  * [What are Privacy-Enhancing Technologies (PETs)? Types & Selection Guide](https://www.syntho.ai/what-are-privacy-enhancing-technologies-pets/)
  * [What Are Privacy-Enhancing Technologies (PETs) And How You Can Choose the Right One(s)](https://www.cpomagazine.com/data-privacy/what-are-privacy-enhancing-technologies-pets-and-how-you-can-choose-the-right-ones/)

{{< figure align=left src="/images/pets-infographic.png" >}}
*via [Enveil](https://www.enveil.com/privacy-enhancing-technologies/)*


#### `Private set intersection (PSI)`
Also called **"double encryption"**. A type of secure multiparty computation "in which each party has a set of items and the goal is to learn the intersection of those sets while revealing nothing else about those sets."
* Read more: [A Brief Overview of Private Set Intersection](https://csrc.nist.gov/presentations/2021/stppa2-psi)
* Related: [*Privacy-enhancing technology (PET)*](#privacy-enhancing-technology-pet), [*Secure multi-party computation*](#secure-multi-party-computation-smpc)

{{< figure align=left src="/images/psi-diagram.png" >}}
*via [Anonos](https://commons.wikimedia.org/wiki/File:Example_PSI_diagram_depicting_basic_security_requirements.png)*


#### `Pseudonymization (tokenization)`
A form of de-identification where personal identifiers are replaced with placeholder values (or "tokens"). Unlike anonymization, pseudonymization does *not* alter the original data, which can still be linked to an individual, and pseudonymization is reversible.
* Read more: 
  * [What is pseudonymization?](https://www.cloudflare.com/learning/privacy/what-is-pseudonymization/)
  * [Pseudonymization](https://cloud.google.com/sensitive-data-protection/docs/pseudonymization)
* Related: [*Privacy-enhancing technology (PET)*](#privacy-enhancing-technology-pet)

{{< figure align=left src="/images/anon-vs-pseudon.png" >}}
*via [Anonos](https://www.anonos.com/)*


## R
#### `Re-identification`
An attack to identify individuals in an "anonymized" dataset using external information and computing techniques to link individuals to their "de-identified" personal information. 

* Read more:
  * [Estimating the success of re-identifications in incomplete datasets using generative models](https://www.nature.com/articles/s41467-019-10933-3)
  * [Re-identification of "anonymized data"](https://georgetownlawtechreview.org/wp-content/uploads/2017/04/Lubarsky-1-GEO.-L.-TECH.-REV.-202.pdf)
  * [The simple process of re-identifying patients in public health records](https://pursuit.unimelb.edu.au/articles/the-simple-process-of-re-identifying-patients-in-public-health-records)
  * [Why 'Anonymous' Data Sometimes Isn't](https://www.wired.com/2007/12/why-anonymous-data-sometimes-isnt/)
* Related: [*Aggregation*](#aggregation)


## S
#### `Secure multi-party computation (S/MPC)`
Also known as **"privacy-preserving computation"**. [Any] "cryptographic protocol that distributes a computation across multiple parties where no individual party can see the other parties’ data."
* Read more: [What is Secure Multiparty Computation](https://inpher.io/technology/what-is-secure-multiparty-computation/)
* Related: [*Privacy-enhancing technology (PET)*](#privacy-enhancing-technology-pet), [*Private set intersection (PSI)*](#private-set-intersection-psi)

{{< figure align=left src="/images/smpc.png" >}}
*via [inpher.io](https://inpher.io/technology/what-is-secure-multiparty-computation/)*


#### `Scream test`
* A test to determine if access to a resource (like personal information, a server, etc.) is still necessary by shutting off access to the resource entirely; if nobody screams bloody murder, then they didn't really need that resource; this can be applied to enforce data minimization
* Read more: [Microsoft uses a scream test to silence its unused servers](https://www.microsoft.com/insidetrack/blog/microsoft-uses-a-scream-test-to-silence-its-unused-servers/)


#### `Software development lifecycle (SDLC)`
The process that an organization follows to design, develop, test, deploy, and maintain software. 
["Shifting privacy left"](https://www.forbes.com/sites/garydrenik/2023/01/18/how-a-companys-philosophy-to-shift-left-is-making-headway-in-the-data-privacy-world/) is the idea to engrain privacy into earlier into product ideation and requirements drafting in order to achieve
[privacy by design](https://cloudsecurityalliance.org/blog/2023/06/09/privacy-by-design-and-privacy-by-default-in-the-cloud).
* Read more: [Integrating Privacy Practices in Software Development Lifecycle](https://www.privado.ai/post/integrating-privacy-practices-in-software-development-lifecycle-sdlc)
* Related: [*Privacy by design*](#privacy-by-design)

{{< figure align=left src="/images/privacy-sdlc.jpg" >}}
*via [Privado](https://www.privado.ai/post/integrating-privacy-practices-in-software-development-lifecycle-sdlc)*


#### `Structured data`
* Organized and machine-readable data that can be queried programatically, such as a relational (SQL) database
* Read more: [Structured vs. Unstructured Data: What’s the Difference?](https://www.ibm.com/blog/structured-vs-unstructured-data/)
* Related: [*Unstructured data*](#unstructured-data)

{{< figure align=left src="/images/structured-vs-unstructured-data.png" >}}
*via [Hevo Data](https://hevodata.com/learn/understanding-structured-data/)*


#### `Static code analysis`
A process to scan the source code of a product to identify personal data to understand how and where it is collected and processed throughout systems.
* Read more:
  * [The case for static code analysis for privacy](https://iapp.org/news/a/the-case-for-static-code-analysis-for-privacy?ref=marcusolsson.dev)
  * [Privacy code scanning: How to sync privacy compliance with software development](https://www.privado.ai/post/privacy-code-scanning-guide?ref=marcusolsson.dev)

{{< figure align=left src="/images/privacy-code-scanning-infographic.png" >}}
*via [Privado](https://www.privado.ai/post/privacy-code-scanning-guide)*


#### `Synthetic data`
* Data, generated by artificial intelligence, that mathematically imitates real-world personal data, which enables orgs to use "privacy-compliant, production-like, and long-retention" data for analytics
* Read more: [What is Synthetic Data?](https://aws.amazon.com/what-is/synthetic-data/)
* Watch: [PEPR '24 - Compute Engine Testing with Synthetic Data Generation](https://www.youtube.com/watch?v=X2c8KambXKg&list=PLbRoZ5Rrl5ldxIsGMFjwixoLxQ1iMq_BH&index=12)


## T
#### `Threat modeling`
A process (originally from cybersecurity) to identify and understand threats to a system and their mitigations. In the context of privacy, this relates to threats to personal information in a system and those data subjects. 
* Read more: [What is privacy threat modeling?](https://www.crowdstrike.com/en-us/cybersecurity-101/threat-intelligence/threat-model/)
* Watch: 
  * [Privacy Threat Modeling: Learn all about it from two experts in the field!](https://www.youtube.com/watch?v=AB8re8inlPw)
  * [PEPR '23 - How to Utilize Your Red Team for Privacy](https://www.youtube.com/watch?v=NEjPZrfK460)


#### `Trusted execution environment (TEE)`
A segregated safe zone within a CPU where only signed code within the environment can be loaded, and all code is "processed in the clear but is only visible in encrypted form when anything outside tries to access it." This ensures that "even if a system is compromised, the data within the TEE remains secure."
* Read more: [Basics of Trusted Execution Environments (TEEs): The Heart of Confidential Computing](https://confidentialcomputing.io/2024/03/13/basics-of-trusted-execution-environments-tees-the-heart-of-confidential-computing/)
* Watch: [ISCA'23 - Lightning Talks - Session1C - TEESec: Pre-Silicon Vulnerability Discovery for Trusted Exec](https://www.youtube.com/watch?v=MTM0SqHNJR4)

{{< figure align=left src="/images/tee-thumbnail.jpg" >}}
*via [Moein Ghaniyoun](https://www.youtube.com/watch?v=MTM0SqHNJR4)*


## U 
#### `Unstructured data`
* Unorganized data that has no pre-defined structure or pattern that makes it difficult(but not impossible) to reliably process and analyze programatically. "More than 80%" of data on the internet is unstructured.
* Read more: [Structured vs. Unstructured Data: What’s the Difference?](https://www.ibm.com/blog/structured-vs-unstructured-data/)
* Related: [*Structured data*](#structured-data)


## Z
#### `Zero knowledge proof`
A "cryptographic mechanism that allows anyone to prove the truth of a statement without having to share the information in a statement."
* Read more: 
  * [Hacker Lexicon: What Are Zero-Knowledge Proofs?](https://www.wired.com/story/zero-knowledge-proofs/)
  * [4 Ways to Compare Trusted Execution Environments and Zero-Knowledge Proofs](https://oasisprotocol.org/blog/comparing-zkp-tee-privacy)

{{< figure align=left src="/images/tee-vs-zkp.png" >}}
*via [Oasis Protocol](https://oasisprotocol.org/blog/comparing-zkp-tee-privacy)*


#### `zk-SNARK`
* Zero-Knowledge Succinct Non-Interactive Argument of Knowledge
* Allows a Prover "[to create] a unique fingerprint for each proof [...] making it impossible to reverse-engineer the original statement. Essentially, these polynomial equations are solvable only by the Prover but verifiable by anyone. They're a puzzle to which only the Prover knows the answer, yet anyone can confirm the answer is correct without knowing what it is."
* Read more: 
  * [What is a zk-SNARK?](https://aleo.org/post/what-is-a-zk-snark/)
  * [What are zk-SNARKs?](https://z.cash/learn/what-are-zk-snarks/)

{{< figure align=left src="/images/zksnark.webp" >}}
*via [Aleo](https://aleo.org/post/what-is-a-zk-snark/)*