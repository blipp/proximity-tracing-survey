# Proximity Tracing

## Authors

* Anne Weine, Inria Paris, Prosecco
* Benjamin Lipp, Inria Paris, Prosecco

Affiliations are listed for completeness and do not imply endorsement.

**Disclaimer:** In this living document the authors are trying to aggregate all information about existing contact/proximity tracing solutions without stating an opinion. The content of this document is based on data available before and on 24th of April, 2020. We will update this “last updated” date whenever updates are made to this document.

Table of Contents:
[TOC]


# Introduction

Public health and administrative staff needs several hours per patient to perform manual contact tracing (See Table 1 in [^ECDC2020]). In order to supplement this process, several actors are currently working on technological proximity tracing solutions.

From https://www.eff.org/fr/deeplinks/2020/04/challenge-proximity-apps-covid-19-contact-tracing

> There are many different proposals for Bluetooth-based proximity tracking apps, but at a high level, they begin with a similar approach. The app broadcasts a unique identifier over Bluetooth that other, nearby phones can detect. To protect privacy, many proposals, including the Apple and Google APIs, have each phone’s identifier rotated frequently to limit the risk of third-party tracking.
> 
> When two users of the app come near each other, both apps estimate the distance between each other using Bluetooth signal strength. If the apps estimate that they are less than approximately six feet (or two meters) apart for a sufficient period of time, the apps exchange identifiers. Each app logs an encounter with the other’s identifier. The users’ location is not necessary, as the application need only know if the users are sufficiently close together to create a risk of infection.
> 
> When a user of the app learns that they are infected with COVID-19, other users can be notified of their own infection risk. This is where different designs for the app significantly diverge.


# Requirements

A “contact tracing” or “proximity tracing” app should supplement/complement the contact tracing work which is usually done manually by health authorities. Different texts have been published about how such an app could achieve this without invading privacy.

* 2020-04-06 [CCC: 10 requirements for the evaluation of "Contact Tracing" apps](https://www.ccc.de/en/updates/2020/contact-tracing-requirements)
* 2020-04-14 [Joint Statement on Contact Tracing from 19th April 2020 by 300+ scientists](https://drive.google.com/file/d/1OQg2dxPu-x-RZzETlpV3lFa259Nrpk1J/view)

## Frequently Asked Questions and Explanations related to Requirements

### Does everybody need to use the app? What if I don't have a smartphone?
Generally, the more people use such an app, the better. But such an app should not be meant to replace manual contact tracing completely – it should still be possible to manually report having been in contact with people in situations where using a smartphone is not possible. Also, due to possible false negatives, people who get infected should still care to inform contacts about whom they know, like for example friends and family which they have met during the infecious time. See also the next point.

### By using a tracing app, you help protect the second hop of the infection.
This means it is less about yourself, but about the community. All the app can do is tell you, that you were in contact with someone who got infected **afterwards**. Now you can take the necessary steps to stop the infection chain here.

# Existing protocols and proposals

:::warning
This section is incomplete and is constantly being updated.
:::

* DP-3T https://github.com/DP-3T/documents
  * 2020-04-08 [Analysis by Serge Vaudenay](https://eprint.iacr.org/2020/399)
* PEPP-PT NTK https://github.com/pepp-pt/pepp-pt-documentation
* ROBERT https://github.com/ROBERT-proximity-tracing/documents
* East Cost PACT https://pact.mit.edu/
* West Coast PACT https://arxiv.org/abs/2004.03544
* Google/Apple API https://www.apple.com/covid19/contacttracing/
* Anonymous Collocation Discovery: Harnessing Privacy to Tame the Coronavirus https://arxiv.org/abs/2003.13670
* Temporary Contact Numbers (TCN) https://github.com/TCNCoalition/TCN https://www.covid-watch.org/
* TraceSecure: Towards Privacy Preserving Contact Tracing https://arxiv.org/abs/2004.04059

## World Overview

* Singapour, TraceTogether: https://www.gov.sg/article/help-speed-up-contact-tracing-with-tracetogether
* Hong Kong: https://www.coronavirus.gov.hk/eng/stay-home-safe.html
* South Corea: http://koreajoongangdaily.joins.com/news/article/Article.aspx?aid=3074299
* China: https://www.sensetime.com/en/news/view/id/141.html, https://www.nytimes.com/2020/03/01/business/china-coronavirus-surveillance.html
* UK: https://www.cl.cam.ac.uk/research/srg/netos/projects/archive/fluphone/
* USA: https://www.media.mit.edu/projects/safepaths/overview/, https://pact.mit.edu/
* Israel: https://www.forbes.com/sites/zakdoffman/2020/03/14/coronavirus-spy-apps-israel-joins-iran-and-china-tracking-citizens-smartphones-to-fight-covid-19/
* Iran: https://siecledigital.fr/2020/03/16/ac19-lapplication-pour-controler-lepidemie-de-covid-19-en-iran/
* Republic of South Africa: https://coviid.me/
* Russia: https://www.bbc.com/news/technology-52121264

# Characteristics of Proposals

Data being sent:
* Type of data sent between end-user devices
* Data volume/time sent between end-user devices
* Data volume/time sent from an end-user device to the internet
* Data volume/time received by an end-user device from the internet

Resistance against attacks:
* Deanonymization (various forms)
* Malicious broadcasting of own IDs
* …

Resistance against the above mentioned attacks when conducted by the following actors:
* end user
* operator of the central infrastructure
* …

Privacy features:
* Does the protocol keep the possibility open to not report certain time slots?

:::warning
TODO start a table summarizing these characteristics for all proposals
:::

# Timeline of Publications and Reactions

:::warning
This section is incomplete and is constantly being updated.
:::

## Governments
* 2020-04-15 ==EU== Mobile applications to support contact tracing in the EU’s fight against COVID-19, Version 1.0 https://ec.europa.eu/health/sites/health/files/ehealth/docs/covid-19_apps_en.pdf
* 2020-04-21 ==Switzerland== ==Adoption== Swiss tracing app will be based on DP-3T https://news.epfl.ch/news/epfl-and-eth-zurich-advance-digital-contact-tracin/
* 2020-04-21 ==EU== [European Data Protection Board: Guidelines 04/2020 on the use of location data and contact tracing tools in the context of the COVID-19 outbreak](https://edpb.europa.eu/our-work-tools/our-documents/guidelines/guidelines-042020-use-location-data-and-contact-tracing_en)
* 2020-04-22 ==France== ==Law== New regulation about data that can be collected and used by health authorities and insurances related to Covid-19 https://www.legifrance.gouv.fr/jo_pdf.do?id=JORFTEXT000041812657
* 2020-04-23 ==Estonia== ==Adoption== [How do you trace Covid-19 while respecting privacy?](https://e-estonia.com/trace-covid-19-while-respecting-privacy/) Estonia will build tracing app based on DP-3T

## Publications

:::warning
TODO add the others
:::

* 2020-04-01 ==Proposal== Leonie Reichert, Samuel Brack, Björn Scheuermann: Privacy-Preserving Contact Tracing of COVID-19 Patients https://eprint.iacr.org/2020/375
* 2020-04-03 ==Proposal== First version of DP-3T published on GitHub
* 2020-04-05 ==Analysis== Nadim Kobeissi, Georgio Nicolas: Formal analysis of DP-3T in Verifpal https://blog.symbolic.software/2020/04/05/dp-3t-verifpal/
* 2020-04-08 ==Proposal== TraceSecure: Towards Privacy Preserving Contact Tracing published on arXiv
* 2020-04-08 ==Analysis== Serge Vaudenay: Analysis of DP3T https://eprint.iacr.org/2020/399
* 2020-04-14 ==Analysis== Yaron Gvili: Security Analysis of the COVID-19 Contact Tracing Specifications by Apple Inc. and Google Inc. https://eprint.iacr.org/2020/428
* 2020-04-17 ==Proposal== First version of ROBERT published on GitHub
* 2020-04-18 ==Proposal== First publication of PEPP-PT NTK on GitHub
* 2020-04-19 ==Analysis== The DP-3T team analyses PEPP-PT and ROBERT https://github.com/DP-3T/documents/tree/master/Security%20analysis

## Scientific Community
* 2020-03-31 [Quantifying SARS-CoV-2 transmission suggests epidemic control with digital contact tracing](https://science.sciencemag.org/content/early/2020/04/09/science.abb6936)
* 2020-04-12 [Ross Anderson: Contact Tracing in the Real World](https://www.lightbluetouchpaper.org/2020/04/12/contact-tracing-in-the-real-world/)
* 2020-04-13 [Bruce Schneier: Contact Tracing COVID-19 Infections via Smartphone Apps](https://www.schneier.com/blog/archives/2020/04/contact_tracing.html)
* 2020-04-17 [Nadim Kobeissi: An Investigation Into PEPP-PT](https://nadim.computer/posts/2020-04-17-pepppt.html) Timeline of events related to PEPP-PT
* 2020-04-18 [ Contact tracing  : Bruno Sportisse, PDG d’Inria, donne quelques éléments pour mieux comprendre les enjeux](https://www.inria.fr/fr/contact-tracing-bruno-sportisse-pdg-dinria-donne-quelques-elements-pour-mieux-comprendre-les-enjeux)
* 2020-04-19 [Joint Statement on Contact Tracing from 19th April 2020 by 300+ scientists](https://drive.google.com/file/d/1OQg2dxPu-x-RZzETlpV3lFa259Nrpk1J/view)
* 2020-04-21 https://risques-tracage.fr/
* 2020-04-23 ==Australia== [Vanessa Teague: Contact tracing and Consent: why using TraceTogether is different from using your memory](https://github.com/vteague/contactTracing/blob/master/blog/2020-04-23ContactTracingAndConsent.md)

## Civil Society

* 2020-04-06 [CCC: 10 requirements for the evaluation of "Contact Tracing" apps](https://www.ccc.de/en/updates/2020/contact-tracing-requirements)
* 2020-04-08 [ACLU: The Limits of Location Tracking in an Epidemic](https://www.aclu.org/sites/default/files/field_document/limits_of_location_tracking_in_an_epidemic.pdf)
* 2020-04-14 [La Quadrature du Net: Nos arguments pour rejeter StopCovid](https://www.laquadrature.net/2020/04/14/nos-arguments-pour-rejeter-stopcovid/)
* 2020-04-24 ==Germany== [CCC: Corona-Tracing-App: Offener Brief an Bundeskanzleramt und Gesundheitsminister](https://www.ccc.de/de/updates/2020/corona-tracing-app-offener-brief-an-bundeskanzleramt-und-gesundheitsminister)

## Press Coverage

* 2020-04-08 ==France== http://www.leparisien.fr/high-tech/coronavirus-le-gouvernement-penche-pour-une-appli-de-tracage-par-bluetooth-08-04-2020-8296368.php
* 2020-04-10 https://www.eff.org/fr/deeplinks/2020/04/challenge-proximity-apps-covid-19-contact-tracing
* 2020-04-15 https://hbr.org/2020/04/how-digital-contact-tracing-slowed-covid-19-in-east-asia
* 2020-04-17 https://www.wired.com/story/apple-google-contact-tracing-strengths-weaknesses/
* 2020-04-22 ==Germany== Coronavirus-App: Infizierte nachverfolgen, Datenschutz wahren https://www.tagesschau.de/investigativ/swr/tracking-app-101.html
* 2020-04-24 ==Germany== [Hanno Böck: Corona-Tracing: Eine App, die nicht zuverlässig funktioniert](https://www.golem.de/news/corona-tracing-eine-app-die-nicht-zuverlaessig-funktioniert-2004-148057.html)

## Development Environment and Technical Considerations
 
### API
* Android Contact Tracing API https://www.blog.google/documents/55/Android_Contact_Tracing_API.pdf/
* iOS Contact Tracing API https://www.apple.com/covid19/contacttracing/
    
### Bluetooth
* 2020-04-22 ==Security==  Remote Code Execution -- CVE-2020-0022 https://insinuator.net/2020/04/cve-2020-0022-an-android-8-0-9-0-bluetooth-zero-click-rce-bluefrag/

# License

This document is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). By this, the authors implement the [Open Covid Pledge](https://opencovidpledge.org/) which lists this license as a compatible license.

# Contribute

You can contribute by opening issues and pull requests on the following GitHub repository, to which this document is frequently synced: https://github.com/blipp/proximity-tracing-survey. You agree that your contributions are published under the license mentioned above. This project adheres to the [Contributor Covenant Code of Conduct v2.0](https://www.contributor-covenant.org/version/2/0/code_of_conduct/). Please contact benjamin dot lipp at inria dot fr for reporting.

# TODO

Completing the existing sections is one task, but also create the following ones:

3) The requirements to an arbitrary protocol for these purposes
5) Key features
6) Attacks 
    a) tracking of individual's movements
    b) trolling: creating (fake) contacts to mark people infected
    c) deanonimisation of an infected person (linkability)
    d) database pollution? Denial of service? False reporting
    e) psychological pressure?
    f) kind of trust needed for central infrastructure (maybe that's for 5) features)
    g) data leakage
    h) Attacks through Bluetooth 
8) Assessment of the attacks (meaning how crucial are they)

# Bibliography

[^ECDC2020]: European Centre for Disease Prevention and Control. Resource estimation for contact tracing, quarantine and monitoring activities for COVID-19 cases in the EU/EEA. ECDC: Stockholm; 2020. https://www.ecdc.europa.eu/sites/default/files/documents/COVID-19-resources-for-contact-tracing-2-March-2020.pdf

