# Exchange Online — External Email Forwarding Investigation

**Category:** Email administration and mail routing  
**Technologies:** Microsoft 365, Exchange Online, Message Trace  
**Status:** Administration boundary identified; forwarding not configured

## Request

A requester wanted all messages received by an external reporting address forwarded to an internal shared mailbox. The reporting service name and all addresses are omitted.

## Recorded investigation

1. Searched the managed Exchange environment for the source address, including mailboxes and recipient groups.
2. Confirmed that the intended destination was an existing shared mailbox.
3. Reviewed outbound traces for messages addressed to the external account.
4. Reviewed separate inbound traces for messages originating from that address.

## Evidence and assessment

The supplied summary described outbound processing as:

```text
Received -> Processed -> Sent
Delivery event: Send external
```

The traces were described as routing mail to another organisation's Microsoft 365 infrastructure. Separate inbound messages reached the managed tenant.

Together with the recipient searches, the recorded findings placed the source address outside the support team's managed mailbox environment. The traces documented the observed routes; they did not prove the external mailbox's complete configuration or its ability to forward every incoming message.

## Recommendation recorded

The requester was advised to contact the administrator responsible for the external mailbox. A rule in the managed tenant was considered only as a partial option: it could affect messages passing through that tenant, but could not guarantee forwarding of all mail received externally.

## Outcome

The routing and administration boundary were explained. No forwarding or transport rule was implemented, and external forwarding was not verified.

## Skills illustrated

Recipient investigation, mail trace interpretation, recognising tenant administration boundaries and assessing the limits of a proposed workaround.
