# Flow Blockchain

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Flow is a developer-friendly Layer 1 proof-of-stake blockchain built for consumer applications, NFTs, games, AI agents, and DeFi at scale. The Flow REST API (Access API) enables developers to query accounts, blocks, collections, events, and transactions, execute Cadence scripts, and submit signed transactions to the network.

## API

- **Base URL (Mainnet):** `https://rest-mainnet.onflow.org/v1`
- **Base URL (Testnet):** `https://rest-testnet.onflow.org/v1`
- **Documentation:** https://developers.flow.com/http-api
- **OpenAPI Spec:** https://raw.githubusercontent.com/onflow/flow/master/openapi/access.yaml

## Endpoints

- `GET /blocks` — Query blocks by height range or list of heights
- `GET /blocks/{id}` — Get blocks by ID
- `GET /blocks/{id}/payload` — Get block payload by block ID
- `GET /transactions/{id}` — Get a transaction by ID
- `GET /transaction_results/{transaction_id}` — Get transaction result
- `POST /transactions` — Submit a signed transaction
- `GET /collections/{id}` — Get a collection by ID
- `GET /execution_results` — Get execution results by block ID
- `GET /execution_results/{id}` — Get execution result by ID
- `GET /accounts/{address}` — Get account data by address
- `GET /accounts/{address}/keys` — Get account keys
- `GET /accounts/{address}/balance` — Get account balance
- `POST /scripts` — Execute a read-only Cadence script
- `GET /events` — Query on-chain events by type
- `GET /subscribe_events` — WebSocket stream for event subscriptions
- `GET /network/parameters` — Get network parameters
- `GET /node_version_info` — Get node version information

## Authentication

No authentication is required for the public community access nodes.

## Rate Limits

Public access nodes enforce per-IP rate limits:

| Endpoint | Limit (RPS) |
|----------|-------------|
| POST /transactions (SendTransaction) | 50 |
| POST /scripts (ExecuteScript) | 5 |
| GET /events | 30 |
| Other GET requests | 100 |

Exceeding limits returns a `ResourceExhausted` error.

## Pricing

API access via public community nodes is free. Transaction fees are paid in FLOW tokens based on compute units consumed. See [finops/finops.yml](finops/finops.yml) for details.

## Resources

- [Developer Portal](https://developers.flow.com/)
- [GitHub Organization](https://github.com/onflow)
- [Flow CLI](https://developers.flow.com/tools/flow-cli)
- [Discord Community](https://discord.gg/flow)
- [Flow Explorer (Flowscan)](https://flowscan.org/)
