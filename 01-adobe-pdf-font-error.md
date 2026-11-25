# Adobe Acrobat — PDF Font Error

**Category:** Application support  
**Technologies:** Outlook, Adobe Acrobat, Adobe Distiller, Windows printing  
**Status:** Fault narrowed down; final repair not confirmed

## Incident

A user reported Outlook crashing or failing while converting emails to PDF. The issue was reported after Adobe subscription and installation changes; a causal link to those changes was not established.

## Recorded investigation

1. Confirmed that the affected laptop had been restarted.
2. Reviewed Outlook COM add-ins and found both Adobe add-ins already disabled.
3. Requested a Microsoft Print to PDF test to help isolate the conversion path. The result was not recorded.
4. Reviewed error information showing an Adobe Distiller font-processing failure.

## Evidence and assessment

The supplied summary recorded these diagnostic messages:

```text
Aptos not found, using Courier
Error: invalidfont; OffendingCommand: show
Warning: PostScript error. No PDF file produced.
```

The error narrowed the investigation to font handling in the Adobe conversion process. Font availability, substitution and conversion configuration remained possible contributors. Disabled Outlook add-ins made an active add-in fault less likely, but did not establish the exact cause of all reported symptoms.

## Proposed next steps — not confirmed completed

- Review Adobe PDF printer preferences, including the setting concerning reliance on system fonts.
- Test conversion with another email and compare the result with Microsoft Print to PDF.
- Refer installation or printer-driver repair to the responsible administrator if needed.

## Outcome

A specific PDF conversion error was identified. No successful repair or confirmed workaround was documented.

## Skills illustrated

Application fault isolation, Outlook add-in checks, diagnostic error interpretation and planning targeted comparison tests.
