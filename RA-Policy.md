# Risk assessment policy

See [CIO 2100.1L – GSA IT Security Policy](https://www.gsa.gov/cdnstatic/CIO_2100_1L_CHGE_1_CC040905_signed_PDF_version_7-15-2019.pdf) 

* Chapter 3, _Policy for Identify Function_, which covers:
  * RA-1, RA-2, RA-3, RA-5
* Chapter 4, _Policy for Protect Function_, which covers:
  * RA-3, RA-5
* Chapter 5, _Policy for Detect Function_, which covers:
  * RA-3, RA-5
* Chapter 6, _Policy for Respond Function_, which covers:
  * RA-3, RA-5

The latest version can be found on the [GSA IT Security Policies](https://www.gsa.gov/about-us/organization/office-of-the-chief-information-officer/chief-information-security-officer-ciso/it-security-policies) page..

## Purpose

Provide governance over a formal, documented risk assessment structure that addresses purpose, scope, controls, roles, responsibilities, management commitment, coordination and compliance.

## Scope

See the **_Applicability_** section of the GSA IT Security Policy.

## Policy overlay

For information on roles and responsibilities, management commitment, coordination among organizational entities, compliance, reviews, and updates please see the [Technology Transformation Service's (TTS) Common Control Policy](https://github.com/cloud-gov/cg-compliance-docs/blob/master/TTS-Common-Control-Policy.md).

<!-- x
changequote(`{{', `}}') 
include({{bq_tts.md}})
x -->
# Procedures

All GSA teams, being part of a federal agency, follow the risk assessment and management process outlined in [NIST Special Publication (SP) 800-37](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-37r1.pdf), _Guide for Applying the Risk Management Framework to Federal Information Systems_.

Initial security categorization is a collaborative and inter-disciplinary activity, with all final decisions made by the Authorizing Official. Risk assessment is similarly cross-functional, with the Cloud Operations team being primarily responsible, as directed by the Program Manager. GSA Information Security teams are consulted throughout, and the Authorizing Official seeks concurrence from the GSA Chief Information Security Officer whenever possible. The Authorizing Official seeks to minimize any need to issue waivers or risk acceptances from GSA IT Security policy (see Chapter 1, Section 5) that do not have concurrence from the GSA Chief Information Security Officer.

See RA-2, RA-3.

Cloud Operations and GSA Information Security work together to scan all of relevant portions of the cloud.gov stack. This includes dynamic scanning of any controls the cloud.gov team is responsible for inside of AWS GovCloud, the operating system baseline of AWS EC2 instances, Cloud Foundry modules, GSA TTS built modules, or any other open source software the team has instantiated within the environment to support cloud.gov. Static code analysis is also performed on the GSA TTS built modules.

Note that _customers_ of cloud.gov are responsible for conducting static code analysis on the baseline of the applications they are deploying into cloud.gov containers.

Access to scanning tools, scan results, and logs is broadly shared amongst the cloud.gov team to ensure a rapid response to any findings. Similarly, on-demand access is granted to the Authorizing Official to aide in any systemic understanding of the system's risk posture.

See RA-5, RA-5(1), RA-5(2), RA-5(3), RA-5(5), RA-5(6), RA-5(8).

cloud.gov leverages GSA's vulnearability disclosure program to satisvy RA-5(11):
- The program should send us, via cloud-gov-compliance@gsa.gov or
  cloud-gov-security@gsa.gov, new Bug Bounty findings
- When receiving a new report, the Assurance team
  - Ensures it has a proper tracking number from GSA IT 
  - Saves the report as a Google doc in the Google Folder 
    ["GitHub Supplemental Information"](https://drive.google.com/drive/folders/1QfLClYg5lw-QPSrLKLEtSEI9ITn5wiYd) 
    with the naming conventiong: `YYYY-MM-DD BBP #NNNNN - short description - product`, e.g.
    `2023-12-07 BBP alert #2247177 - improper access control - Pages`
  - Creates a GitHub issue for the appropriate team, referencing the document
- Notifies the team via Slack

The assurance team should track the issue either as bug (if Low severity) or
as a finding if Medium or High severity). 


# Version history

Complete version history: https://github.com/cloud-gov/cg-compliance-docs/commits/master/RA-Policy.md

* 2016-10: Initial version for authorization
* 2017-09: Security policy link updates
* 2019-12: Update links to GSA security policy
* 2020-11: Update links to GitHub and GSA policies, split controls by CSF, add version history
* 2021-11: Correct to using GSA TTS as organization name
* 2023-12: Add VDP process
