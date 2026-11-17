# mta-sts.arya-tech.net

The MTA-STS policy for `arya-tech.net` (RFC 8461), served by GitHub Pages at
`https://mta-sts.arya-tech.net/.well-known/mta-sts.txt`.

- **Mode: testing.** Sending servers report TLS problems (to the TLS-RPT
  address in `_smtp._tls.arya-tech.net`) but still deliver. Move to
  `enforce` only after a few weeks of clean reports.
- `mx` must list every MX host of `arya-tech.net` (today: `smtp.google.com`).
  If the MX changes, change this file first.
- **Any change to the policy file needs a new `id` in the
  `_mta-sts.arya-tech.net` TXT record** (`v=STSv1; id=<new value>`), or
  senders keep the cached copy for up to `max_age` (7 days).

`.nojekyll` makes Pages serve the `.well-known` folder.
