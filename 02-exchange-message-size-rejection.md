# Exchange Online and Mimecast — Message Size Rejection

**Category:** Email administration and mail flow  
**Technologies:** Exchange Online, Mimecast, Microsoft 365  
**Status:** Rejection cause identified; successful redelivery not verified

## Incident

An expected email with attachments did not arrive in a shared mailbox. It appeared in Mimecast but was absent from the recipient's Outlook view.

## Recorded investigation

1. Located the message in Mimecast with an archived status.
2. Checked Exchange Online Message Trace and identified a failed delivery event.
3. Compared the message size with the recipient mailbox's receiving limit.
4. Reviewed the trace indication that a non-delivery report had been sent to the sender.

## Evidence and assessment

```text
550 5.2.3 RESOLVER.RST.RecipSizeLimit
Message too large for this recipient
```

The recorded message size exceeded the mailbox's configured receiving limit. Exact sizes and configuration values are omitted for confidentiality.

Mimecast archiving did not establish delivery to the Exchange mailbox. The Exchange rejection explained the missing message. The trace recorded that an NDR was sent; it did not establish whether the sender read it.

## Advice recorded

The requester was advised to ask for smaller attachments or an approved secure file-sharing link. A mailbox-limit change was not considered necessary for the isolated message; no such change was documented.

## Outcome

The delivery rejection cause was identified and explained. Successful resend and receipt were not verified.

## Skills illustrated

Cross-system mail investigation, Exchange Message Trace, SMTP error interpretation, size-limit comparison and evidence-based communication.
