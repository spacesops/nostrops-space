# NostrOps

**NostrOps** is short for **Nostr Operators**: administrators of [Nostr](https://github.com/nostr-protocol/nostr) relay servers.

This repository is a static multi-page field guide covering operator concerns, relay types, operational best practices, common relay software, and the NIPs that belong on an operator’s desk.

Open [`index.html`](index.html) in a browser, or serve the folder:

```bash
python3 -m http.server 8765
```

Then visit [http://127.0.0.1:8765/](http://127.0.0.1:8765/).

## Pages

| Page | Contents |
| --- | --- |
| [Home](index.html) | What a relay operator is, and a map of the guide |
| [Concerns](concerns.html) | Spam, disk growth, policy vs protocol, jurisdiction, the free-relay commons, admin surfaces |
| [Relay types](types.html) | Personal allowlist, community web-of-trust, paid public, specialized |
| [Practices](practices.html) | TLS, NIP-11, ingest filters, resource caps, NIP-42, systemd, backups, NIP-86 lockdown |
| [Software](software.html) | strfry, nostr-rs-relay, nostream, khatru/rnostr/nostrd, GRAIN and filter proxies |
| [NIPs](nips.html) | 01, 11, 13, 22, 40, 42, 77, 86 |
| [Sources](sources.html) | Links to the NIPs and production guides this site synthesizes |

## Layout

```
.
├── index.html
├── concerns.html
├── types.html
├── practices.html
├── software.html
├── nips.html
├── sources.html
├── styles.css
├── fonts/              # Self-hosted OFL typefaces
├── images/
│   ├── logo.png
│   ├── favicon.ico
│   ├── apple-touch-icon.png
│   ├── hero-banner.jpg
│   ├── network.jpg
│   ├── concerns.jpg
│   └── practices.jpg
└── README.md
```

No build step. No JavaScript. Figtree, Fraunces, and IBM Plex Mono are self-hosted under `fonts/` (SIL Open Font License).

## Deploy

Any static host works. For GitHub Pages, publish the repository root (`index.html` at `/`).

To publish as an [nsite](https://nsyte.run/) (NIP-5A on Nostr + Blossom):

```bash
# Pair once with a NIP-46 bunker, then:
nsyte bunker connect 'bunker://…'
nsyte bunker use <bunker-pubkey>
nsyte deploy .
```

Config lives in `.nsite/config.json`. This project deploys as the named site `nostrops` so it does not overwrite a root nsite or profile on the same key. Credentials stay in the OS keychain, not in the repo.

Live nsite (SpacesOps bunker, named site `nostrops`):

- https://0aqfaabvyoyl4l5dhocm4gu80l4xlj6bpt2sra31t16g9o7vsjnostrops.nsite.lol/
- https://0aqfaabvyoyl4l5dhocm4gu80l4xlj6bpt2sra31t16g9o7vsjnostrops.nwb.tf/
- https://0aqfaabvyoyl4l5dhocm4gu80l4xlj6bpt2sra31t16g9o7vsjnostrops.nsite.run/

## Sources

The site is a synthesis, not a substitute for the originals:

- [NIP-11 — Relay Information Document](https://nips.nostr.com/11)
- [NIP-86 — Relay Management API](https://nips.nostr.com/86)
- [Run Your Own Nostr Relay (D-Central)](https://d-central.tech/run-your-own-nostr-relay-bitcoiners/)
- [LearnNostr — Relay Setup](https://learnnostr.org/getting-started/relay-setup)
- [deploynode — Run a Nostr relay](https://deploynode.io/guides/run-a-nostr-relay)
- [hoytech/strfry](https://github.com/hoytech/strfry)
- [scsibug/nostr-rs-relay](https://github.com/scsibug/nostr-rs-relay)
- [Web of Trust on Nostr](https://nostr.co.uk/news/web-of-trust-on-nostr/)
