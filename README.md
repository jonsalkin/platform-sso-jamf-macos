# platform-sso-jamf-macos

Deployment notes and troubleshooting log for rolling out Platform SSO (PSSO) with Okta Verify across a Jamf-managed macOS fleet.

## Problem

Platform SSO lets macOS use a cloud identity provider for local account authentication and unlock, tying device-level login to the same identity used for every other app. It is still a relatively new deployment pattern with limited public documentation on real-world rollout issues.

## Approach

Validated the configuration profile and Okta Verify PSSO extension on a single test machine before fleet-wide rollout, then worked through authentication failures encountered on additional test accounts to isolate whether the issue was profile scope, account state, or the extension itself.

## What's Documented

- The Jamf configuration profile structure used to deploy the PSSO extension and register it with Okta Verify
- The validation steps used to confirm PSSO was working correctly on a test machine (successful local login tied to the Okta identity)
- A troubleshooting log of authentication failures encountered on subsequent test accounts, including the diagnostic steps taken to narrow down the cause

## Tech Stack

- Jamf Pro (configuration profiles, smart groups for staged rollout)
- Okta Verify (PSSO extension)
- macOS Platform SSO framework

## Notes

Device names, enrollment IDs, and organization-specific configuration profile values have been replaced with placeholders. This is intended as a rollout and troubleshooting reference, not a copy-paste deployment package, since PSSO configuration is tenant- and MDM-specific.

---

**Security note:** Never commit real credentials, API keys, tenant IDs, internal URLs, or any company-identifying data. Replace with placeholders before publishing, and check commit history too.
