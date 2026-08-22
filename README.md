# Castr (castr-live)

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

Castr is a live video streaming, multistreaming, and video-hosting (VOD) platform. You ingest a single RTMP or SRT source and Castr restreams it to multiple destinations (YouTube, Facebook, custom RTMP, and more), records and clips live streams, hosts and delivers on-demand video, runs ultra-low-latency sub-second (WebRTC) streams, and embeds a player.

Castr exposes a **documented, self-serve REST API** at `https://api.castr.com/v2`. You create a Castr account, generate an API token from the account settings API section (`https://castr.com/app/manage/api`), and send it in an `authorization` header. The API covers live streams and their multistream platform destinations, sub-second streams, video hosting folders and uploads, live-to-VOD recordings, activity logs/events and stream stats, and webhook endpoints.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/castr-live/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/castr-live/refs/heads/main/apis.yml)

## Access Model

- **Public and self-serve.** Anyone can sign up, get an API token from settings, and call the documented API. No sales contact or partner gating is required to read the reference or obtain a token.
- **Included with a paid plan.** API access ships with Castr subscription plans (a free trial is offered). Concurrency, bandwidth, and storage scale with the tier rather than the API being locked behind an enterprise-only plan.
- **Auth:** API token in an `authorization` header (confirmed by a published curl example). Base URL `https://api.castr.com/v2`; resource paths are snake_case (e.g. `/live_streams`).

## Modeling Note

Endpoint paths, methods, and resource groupings in this entry come from Castr's published developer reference and its machine index (`developers.castr.com`, including `llms.txt`). The request/response JSON schemas in the OpenAPI are **honestly modeled** from the documentation rather than copied from a Castr-published OpenAPI file, so property-level detail should be verified against the live reference (`endpointsModeled: true` in `review.yml`).

## Tags

- Live Streaming
- Multistreaming
- Video Hosting
- VOD
- Restreaming
- Sub-Second Streaming
- WebRTC
- Analytics
- Webhooks

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Castr Live Streams API

Create, list, get, update, and delete live streams; retrieve stream stats and the live EPG; and manage the multistream platform destinations a stream restreams to. Streams ingest RTMP or SRT and fan out to multiple destinations and CDNs.

- **Human URL:** [https://developers.castr.com/reference/get_v2-live-streams](https://developers.castr.com/reference/get_v2-live-streams)
- **Base URL:** `https://api.castr.com/v2`

### Castr Sub-Second Streams API

Create, list, get, update, and delete sub-second (ultra-low-latency, WebRTC-based) streams for interactive and real-time use cases where standard HLS latency is too high.

- **Human URL:** [https://developers.castr.com/docs/create-sub-second-streams](https://developers.castr.com/docs/create-sub-second-streams)
- **Base URL:** `https://api.castr.com/v2`

### Castr Video Hosting and VOD API

Manage video hosting folders and contents, create direct upload URLs for on-demand videos, retrieve temporary live-stream recordings, and convert live recordings into permanent VOD assets (Live-to-VOD).

- **Human URL:** [https://developers.castr.com/docs/post-a-video](https://developers.castr.com/docs/post-a-video)
- **Base URL:** `https://api.castr.com/v2`

### Castr Analytics and Activity API

Retrieve activity logs and events for a stream or video and pull per-stream stats (online status, duration, bitrate, codec, viewers) for real-time monitoring.

- **Human URL:** [https://developers.castr.com/docs/create-a-livestream-pu](https://developers.castr.com/docs/create-a-livestream-pu)
- **Base URL:** `https://api.castr.com/v2`

### Castr Webhooks API

Register, list, update, and delete webhook endpoints so Castr can push stream and video lifecycle events (online/offline, recording ready, upload complete) to your own systems.

- **Human URL:** [https://developers.castr.com/reference](https://developers.castr.com/reference)
- **Base URL:** `https://api.castr.com/v2`

## WebSocket Review

Castr does **not** expose a documented public WebSocket API. Its own API is request/response REST, and push-style event delivery to developers is via outbound HTTP **webhooks**, not WebSocket. The realtime media transports — RTMP/SRT ingest, HLS/WebRTC delivery, and RTMP restreaming — are media protocols, not a subscribe-style WebSocket API, so no AsyncAPI document was created. See [review.yml](review.yml).

## Common Properties

- [Website](https://castr.com)
- [LinkedIn](https://www.linkedin.com/company/castr-live)
- [Documentation](https://developers.castr.com/docs/getting-started)
- [API Reference](https://developers.castr.com/reference/get_v2-live-streams)
- [Sign Up / API Keys](https://castr.com/app/manage/api)
- [Pricing](https://castr.com/pricing/)
- [Plans](plans/castr-live-plans-pricing.yml)
- [Rate Limits](rate-limits/castr-live-rate-limits.yml)
- [Fin Ops](finops/castr-live-finops.yml)
- [Blog](https://castr.com/blog/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
