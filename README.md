# unfoldingdimensions.github.io

Redirect-only site. Every page here forwards to the canonical copy on
**unfoldingdimensions.com**, which is the domain declared for payment
verification.

| Path | Forwards to |
|---|---|
| `/` | `unfoldingdimensions.com/privacy` |
| `/Terms` | `unfoldingdimensions.com/terms` |
| `/Buy` | `unfoldingdimensions.com/ghl-workflow-backup#buy` |

## Why keep it alive at all

These URLs were published before the custom domain existed, and some are
registered in places that can't easily be changed retroactively — notably the
**Privacy Policy URL on the Chrome Web Store listing** for the *GHL Workflow
Backup & Audit* extension. Removing them would break those references.

GitHub Pages serves static files and can't issue a 301, so each page does the
client-side equivalent: `rel=canonical` for crawlers, `meta refresh` for
scripting-off browsers, `location.replace` for everyone else (replace, not
assign, so Back doesn't bounce the visitor straight back), and a visible link as
the final fallback.

## Do not re-add policy content here

Policy text lived in this repo as markdown until 2026-08-18 and drifted out of
date — it still described the payment provider as "merchant of record" weeks
after that stopped being true, on the page a Chrome Web Store reviewer reads.
One canonical copy, on unfoldingdimensions.com. Edit it there.
