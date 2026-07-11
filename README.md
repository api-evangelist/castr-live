# Castr (castr-live)

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
