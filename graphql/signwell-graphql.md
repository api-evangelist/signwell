# SignWell GraphQL Schema

This document describes the conceptual GraphQL schema for the SignWell e-signature API. SignWell provides a REST API at https://www.signwell.com/api/v1 for sending documents for electronic signature, managing templates, tracking document status, running bulk sends, and configuring webhooks. This GraphQL schema represents those capabilities as a typed graph.

## Source

- API Reference: https://developers.signwell.com/reference/getting-started-with-your-api-1
- Base URL: https://www.signwell.com/api/v1

## Schema Overview

The schema covers the following domains:

### Documents
Core document lifecycle types: `Document`, `DocumentDetails`, `DocumentStatus`, `DocumentType`, `DocumentAuditLog`, `AuditEntry`. Documents are the central resource — they are created, sent to signers, tracked, and completed.

### Templates
Reusable document templates: `Template`, `TemplateDetails`, `TemplateField`. Templates allow pre-configured documents with placeholder fields that are filled at send time.

### Signers
People who sign documents: `Signer`, `SignerDetails`, `SignerOrder`, `SignerSMS`. Signers are associated with documents and may be ordered sequentially.

### Signatures
Captured signature data: `Signature`, `SignatureDetails`, `SignatureDate`, `SignatureIP`. These represent the cryptographic and metadata aspects of a completed signature event.

### Fields
Document fields for data collection: `Field`, `FieldDetails`, `FieldType`, `FieldValue`. Fields can be signature boxes, initials, text inputs, dates, checkboxes, and more.

### Files
Document file sources: `File`, `FileDetails`, `FileSource`. Files are the underlying PDFs or documents attached to a document or template.

### Attachments
Supporting file attachments: `Attachment`, `AttachmentDetails`. Signers can be required to attach files as part of the signing process.

### Teams and Users
Account organization: `Team`, `TeamDetails`, `TeamMember`, `User`, `UserDetails`, `UserRole`. Teams group users within an account.

### Account
Account-level configuration: `Account`, `AccountDetails`, `AccountType`. Represents the top-level organizational entity.

### Authentication
API access control: `APIKey`, `Token`. Used for authenticating requests to the SignWell API.

### Webhooks
Event-driven integrations: `Webhook`, `WebhookEvent`. SignWell fires webhook events for document lifecycle changes.

### Bulk Send
Mass sending capability: `BulkSendJob`, `BulkSendJobDetails`, `BulkSendJobStatus`. Allows sending the same document to many recipients at once.

### Scheduling and Reminders
Automated follow-ups: `Reminder`, `Expiration`. Configures automatic reminder emails and document expiration.

### Metadata and Branding
Customization: `Metadata`, `Branding`, `BrandingDetails`. Allows white-label customization of the signing experience.

### Embedded Signing
Iframe-based signing: `FormEmbed`, `EmbedUrl`, `EmbedSession`. Enables embedding the signing UI directly in a host application.

## Type Count

55 named types defined in `signwell-schema.graphql`.
