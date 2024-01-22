# Access control policy

See [CIO 2100.1L – GSA IT Security Policy](https://www.gsa.gov/cdnstatic/CIO_2100_1L_CHGE_1_CC040905_signed_PDF_version_7-15-2019.pdf)

* Chapter 3, _Policy for Identify Function_, which covers:
  * AC-1, AC-4, AC-20
* Chapter 4, _Policy for Protect Function_, which covers:
  * AC family controls
* Chapter 5, _Policy for Detect Function_, which covers:
  * AC-2, AC-4, AC-25

The latest version can be found on the [GSA IT Security Policies](https://www.gsa.gov/about-us/organization/office-of-the-chief-information-officer/chief-information-security-officer-ciso/it-security-policies) page.

## Purpose

Limit information system access to authorized users or processes acting on behalf of authorized users. Enforce "least privilege" methodologies for all system actions.

## Scope

See the **_Applicability_** section of the GSA IT Security Policy.

## Policy overlay

For information on roles and responsibilities, management commitment, coordination among organizational entities, compliance, reviews, and updates please see the [Technology Transformation Service's (TTS) Common Control Policy](https://github.com/cloud-gov/cg-compliance-docs/blob/master/TTS-Common-Control-Policy.md).

<!-- x
changequote(`{{', `}}') 
include({{bq_tts.md}})
x -->

# Procedures

cloud.gov's access control procedures starts with an offer letter to an individual from the GSA Office of Human Resources Management (OHRM). As the individual is on-boarded to the federal government, their personal information is recorded, biometrics are taken, preexisting identification is validated, and finally a personal identity verification (PIV) card is issued in full accordance with  Homeland Security Presidential Directive 12 (HSPD-12).

Successfully issuing a PIV card allows internal users to obtain credentials for GSA SecureAuth, GSA's enterprise identity system. GSA SecureAuth is used to gate access control to cloud.gov's Operations User Account and Authentication (UAA) Server, which is integrated with GSA SecureAuth. 

Technical onboarding to cloud.gov is initiated by the cloud.gov Director, Deputy Director, or Program Manager via creation of an Onboarding issue in the cloud.gov issue tracking system. The issue should include the On-boarding Checklist (https://github.com/cloud-gov/product/blob/main/.github/ISSUE_TEMPLATE/onboard-platform-ops.md) which ensures the internal user gains proper access and permissions to any systems or tools they need, inclusive of access to Amazon Web Services (AWS). Access to AWS is strictly limited to the System Owner, Cloud Operations, and Cloud Compliance (read-only). The Cloud Operations team member assigned to the issue acts on it once the individual has GSA SecureAuth access and a GSA email account.

The System Owner (or representative) and a quorum of the Cloud Operations meet on a quarterly
basis to review and confirm all team accounts meet requirements for compliance
with account management needs. Typically these meetings occur in March, June,
September and December. In advance of the meeting, members of the compliance team
and cloud operations will generate reports of group memberships and role
assignments. During the meeting, the participants 
will review memberships and their alignment with current
job responsibilies, and make changes, or assign issues, to make corrections.
All team member roles should align with contingency plan roles on the "cloud.gov Team Roster"
(Google Docs). Should the team size exceed 24, account review will include
account activity audits to ensure access is still required for job functions.

When a privileged team member has been absent (leave, illness, detail assignment)
for more than 30 days, or is scheduled to be absent for 30 or more days, the System Owner
disables their privilege rights from their accounts (AWS, cloud foundry and GitHub). 
When the individual returns to work, the System Owner reinsates/restores those account privileges. 

When a privileged team member is terminated, reassigned or loses their need to know rights, 
the System Owner permanently disables their privilege rights and access from all accounts within 24 hours
of departure.

See SSP controls AC-2, AC-2(1), AC-2(2), AC-2(3), AC-2(4), AC-2(5), AC-2(7), AC-2(9), AC-2(10), AC-2(12), AC-3, AC-7, AC-8, AC-11, AC-11(1), AC-12, AC-14, AC-17, AC-17(1), AC-17(2), AC-17(4).

cloud.gov's customers gain access to the system in a similar fashion. The Client UAA Server can integrate with any enterprise identity system that supports the Security Assertion Markup Language (SAML) standard. Cloud Operations and the customer follow a simple procedure (https://cloud.gov/docs/ops/federated-identity/) in order to complete the integration. For cloud.gov customers using the cloud.gov identity provider, customer accounts will be deactivated after not logging into the system after 90 days.

See SSP controls AC-2(9), AC-2(10), AC-21.

The cloud.gov infrastructure service does have an emergency fallback
"breakglass" account with keys that are kept in secure storage. Any
use of the breakglass credentials generates alerts to Cloud Operations. We
have code to rotate those credentials on-demand.

See SSP controls AC-2(1)


Within cloud.gov, both the permissions of users (whether internal or external) and the logical flow of data through the system is tightly controlled and regulated. Manual movements of data are strictly prohibited. Everything is subject to the virtual network, application, and container restrictions that are instantiated through cloud.gov's adherence to immutable "infrastructure as code."

See SSP controls AC-4, AC-4(21), AC-17(3), AC-17(9), AC-19, AC-20 (2), and the CM controls.

GSA systems always adhere to the principle of role segmentation and least privilege wherever possible.

See SSP controls AC-5, AC-6, AC-6(1), AC-6(2), AC-6(5), AC-6(9).

# Version history

Complete version history: https://github.com/cloud-gov/cg-compliance-docs/commits/master/AC-Policy.md

* 2016-10: Initial version for authorization
* 2017-09: Security policy link updates
* 2019-12: Update links to GSA security policy
* 2020-11: Update links to GitHub and GSA policies, split controls by CSF, add version history
* 2021-02: Customer accounts will be deactivated after not logging into the system after 90 days.
* 2021-11: Reviewed by @pburkholder, no changes
* 2022-04: Include additional guidance for details, leave, extended absences, and terminations
* 2024-01: Annual Review. No updates.
