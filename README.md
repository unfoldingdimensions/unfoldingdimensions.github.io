# Privacy Policy — GHL Workflow Backup & Audit

**Last updated:** 2026-08-11

This extension is built to export your own GoHighLevel workflow data for your
own use. This policy explains exactly what data it touches, where it goes, and
what it never does.

## What the extension reads

When you use the extension on a GoHighLevel workflow page
(`app.gohighlevel.com`), it reads the workflow's step-tree data (nodes,
triggers, settings, and — if you provide an API token, see below — the
human-readable names of things the workflow references, like pipelines,
calendars, tags, and users). This is your own account's data, read directly
from the page or GoHighLevel's own API; the extension does not access any
other GoHighLevel account or any data outside the workflow(s) you choose to
export.

### How it reads workflow data (network response inspection)

GoHighLevel's workflow builder does not expose a workflow's full step-tree in
the page's HTML, and its public API does not return one either. To assemble a
complete export, the extension therefore does two things on GoHighLevel pages:

1. **Reads the builder's in-memory state** (its JavaScript application data)
   for the workflow you have open.
2. **Inspects the responses of network requests the GoHighLevel page itself
   makes**, as a fallback when in-memory state isn't available, and to learn the
   names of items referenced by the workflow. It does this by wrapping the
   page's own `fetch` and `XMLHttpRequest` so it can read response bodies as
   they arrive.

This inspection is limited to responses from GoHighLevel's own domains
(`gohighlevel.com`, `leadconnectorhq.com`, `msgsndr.com`) and the Firebase
datastore its builder uses. Requests to any other domain, and static assets
(scripts, stylesheets, images, fonts, media), are ignored and never read.

Response data is used only to build the export file you asked for, is held in
memory for the duration of the capture, and is **never transmitted to us or to
any third party**. It goes only to the destination you choose below. The
extension does not read, record, or transmit your browsing activity on any
other site — its content scripts run only on the GoHighLevel domains listed in
its manifest.

## Where that data goes

You control the destination in the extension's Options page:

- **Local download** (default): the exported JSON file is saved directly to
  your browser's Downloads folder on your own device. This data never leaves
  your computer.
- **Google Drive** (optional): if you enable this, the exported JSON is
  uploaded to a folder named "GHL Workflow Exports" in **your own** Google
  Drive, using a Google sign-in you grant directly to the extension via
  Google's standard OAuth flow. The extension can only see files/folders it
  itself creates (Google's `drive.file` permission scope) — it cannot browse,
  read, or modify any other file in your Drive.
- **Both**: does both of the above.

In no case does the extension send your workflow data to the developer, to
any analytics service, or to any third party other than the destination you
explicitly choose above.

## The GoHighLevel API token (optional)

If you add a GoHighLevel Private Integration Token in Options, it is stored
only in your browser's local extension storage (`chrome.storage.local`,
never synced to Google or anywhere else) and is sent only to
`services.leadconnectorhq.com` — GoHighLevel's own official API — to resolve
IDs (like a pipeline or tag ID) into human-readable names for your export.
The extension never transmits this token anywhere else.

## Licensing and payment (paid version)

If you purchase a license, checkout is handled entirely by a third-party
payment provider acting as the merchant of record. The extension never sees or
stores your payment card details. After a successful payment they send us the
email address you paid with, and we generate a license key tied to it. The
extension stores only that license key locally (`chrome.storage.local`) and
sends it to our license-verification server to confirm it's valid. We do not
sell, rent, or share your email address or license information with any third
party other than our payment provider (as required to process the transaction)
and our license-verification infrastructure.

See the [Terms of Sale & Refund Policy](https://unfoldingdimensions.com/terms)
for pricing, delivery and refund terms.

## What we never collect

- No analytics, telemetry, or usage tracking of any kind.
- No browsing history outside the specific GoHighLevel pages you use the
  extension on.
- No data sold to advertisers or data brokers.

## Data retention & deletion

Local download and Drive-uploaded files are yours — delete them like any
other file. Your GHL token and Drive-folder cache live only in your browser's
local extension storage and are deleted automatically if you remove the
extension, or manually via the Options page. To request deletion of
license/email records tied to a purchase, contact us below.

## Changes to this policy

If what data we collect or how we use it changes, we will update this page
and, for any material change, notify users through the extension or the
Chrome Web Store listing before the change takes effect.

## Contact

Questions about this policy: **unfoldingdimensions@gmail.com**
