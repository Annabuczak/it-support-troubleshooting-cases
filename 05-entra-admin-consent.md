# Microsoft Entra ID — Application Administrator Consent

**Category:** Identity and access troubleshooting  
**Technologies:** Microsoft Entra ID, enterprise applications, OpenID Connect  
**Status:** Administrator approval requirement identified; review outstanding

## Incident

A newly onboarded user could not sign in to an external business application with an organisational Microsoft account. The provider suggested that a tenant authorisation relationship had been removed. That explanation was not verified.

## Evidence and assessment

The supplied summary described an OpenID Connect integration and an authentication screen stating:

```text
Need admin approval
```

The screen indicated that the application requested access requiring administrator approval. It did not establish that a tenant trust relationship had been removed or identify why consent was now required.

Possible explanations included missing administrator consent, changes to consent policy, changed permissions or a changed application registration. None was confirmed.

## Proposed investigation — not confirmed completed

1. Locate the application in the intended Entra tenant.
2. Verify its identity and publisher and review the requested permissions.
3. Inspect existing consent and any pending approval request.
4. Review relevant user sign-in evidence.
5. Refer any consent decision to an appropriately authorised administrator.

The source did not establish which administrator role was required for the specific permission request. A provider's request for a named role was not treated as proof of that requirement.

## Permission review

Any proposed approval would require review of the application's business purpose, permission scope and impact. The approval prompt alone was not a reason to grant consent or change tenant trust settings.

## Outcome

The immediate administrator approval requirement was identified. No permission changes, completed administrator investigation or successful sign-in were confirmed.

## Skills illustrated

Interpreting an authentication prompt, distinguishing evidence from a provider's hypothesis, planning an application-permission review and recognising escalation boundaries.
