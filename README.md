# Awesome-Video-Hosting-Streaming-Platform

# Awesome Video Hosting & Streaming Platform

> A curated list of top Video Hosting and Streaming platforms — both SaaS/Hosted commercial solutions and open-source alternatives for managing, publishing, and delivering video content.  
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Vimeo Enterprise](#vimeo-enterprise)
  - [Brightcove](#brightcove)
  - [Wistia](#wistia)
  - [Vidyard](#vidyard)
  - [Kaltura](#kaltura)
  - [Panopto](#panopto)
  - [Dacast](#dacast)
  - [SproutVideo](#sproutvideo)
- [Open-Source Software](#-open-source-software)
  - [MediaCMS](#mediacms)
  - [Mave Core](#mave-core)
  - [Hovod](#hovod)
  - [AVideo](#avideo)
  - [Owncast](#owncast)
  - [MediaMTX](#mediamtx)
  - [Tape](#tape)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Video Hosting and Streaming platforms. These are not open-source but are included as reference points for feature comparison.

### Vimeo Enterprise
**Type:** Video hosting and collaboration platform  
Vimeo is best known for its user-friendly video hosting and collaboration tools, appealing to marketers, agencies, and creative teams. Plans are built around uploading, organizing, and sharing content, with a branded HTML5 player that is easy to embed [citation:1]. Its main strength is usability — uploading videos, grouping them into folders or showcases, and sharing links or embeds requires minimal configuration. Collaboration tools like team workspaces and feedback features help creative teams manage revisions. **Trade-offs:** Limited player-level customization compared to developer-focused platforms, and monetization features are packaged on higher tiers rather than offering granular ad-tech control [citation:1]. Live streaming is available but only as an add-on on upper tiers, with a 12-hour event cap [citation:14].

### Brightcove
**Type:** Enterprise video platform for large organizations and broadcasters  
Brightcove is aimed at large organizations, broadcasters, and media companies, covering live streaming, VOD, marketing, and OTT distribution under one umbrella. It is built to plug into complex workflows, CRMs, and marketing automation systems, and to serve large audiences with bespoke support. Analytics and reporting are central, with detailed audience engagement tracking tied into marketing tools [citation:6]. **Trade-offs:** Sales-driven quote-based pricing creates onboarding friction for smaller teams, and the platform’s complexity may exceed what mid-market organizations need [citation:6].

### Wistia
**Type:** Video marketing and hosting platform  
Wistia focuses on video marketing for businesses, with features for embedding, analytics, lead capture, and video SEO. It is known for its player customization and marketing integrations, positioning itself between consumer hosting (Vimeo) and enterprise platforms (Brightcove).

### Vidyard
**Type:** Video hosting for sales and marketing  
Vidyard specializes in video for sales outreach and marketing, with tools for recording, hosting, analytics, and integrating video into CRM workflows. Its focus is on using video as a sales enablement and lead generation tool rather than general-purpose hosting.

### Kaltura
**Type:** Enterprise video platform and video CMS  
Kaltura provides enterprise video solutions spanning hosting, streaming, video portals, and virtual events. It is often used by educational institutions and large enterprises needing a comprehensive video CMS with access control and analytics.

### Panopto
**Type:** Video platform for education and enterprise  
Panopto specializes in video content management for education and training, with lecture capture, video CMS, and searchable transcripts. It is widely deployed in universities and corporate learning environments.

### Dacast
**Type:** Live streaming-first video platform  
Dacast is built around live streaming with VOD fully supported, offering publicly documented plans (Starter, Event, Scale) with unlimited concurrent viewers and live channels on all plans [citation:10]. It emphasizes full white-label streaming so viewers do not see the Dacast brand, making it suitable for broadcasters and enterprises wanting a first-party look [citation:10]. Built-in monetization includes pay-per-view, subscriptions, and advertising support [citation:6].

### SproutVideo
**Type:** Business video hosting with marketing features  
SproutVideo provides video hosting for businesses with customizable players, lead capture forms, analytics, and privacy controls. It positions itself as a user-friendly alternative for marketing and internal communications videos.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Video Hosting and Streaming platforms. All listed projects offer source code you can deploy on your own infrastructure.

### MediaCMS
**Stack:** Python / Django / React / Celery | **License:** AGPL-3.0  
A modern, fully featured open-source video and media CMS designed to build small to medium video and media portals. Supports video, audio, image, and PDF media types, with multiple publishing workflows (public, private, unlisted, custom) [citation:3]. Features include **adaptive HLS streaming**, multiple transcoding profiles (144p to 1080p; h264, h265, vp9), role-based access control, SAML support, playlists, subtitles/CC, and automatic transcription via Whisper [citation:13]. The player is a customized video.js with resolution switching and playback speed options. Deploys via Docker Compose. Hardware guidance: 4GB RAM / 2-4 CPUs minimum for small to medium installations [citation:3].  
**Best for:** Organizations wanting a self-hosted YouTube-like video portal with adaptive streaming, transcoding, and access control.

### Mave Core
**Stack:** Elixir / Phoenix / FFmpeg / PostgreSQL / ClickHouse / S3 | **License:** Open Source (per repository)  
An open-source video platform with a dashboard, programmable encoding pipeline, embeddable player, and built-in analytics. Uploads run through a versioned DAG that inspects the source, encodes renditions, packages HLS, and generates visual assets [citation:5]. Media is stored in **your own S3-compatible storage** (MinIO bundled as default). Features include resumable uploads, adaptive HLS, posters, subtitles, customizable player settings, and analytics backed by your own ClickHouse instance. Deploys via `docker compose up` with PostgreSQL, ClickHouse, MinIO, tusd, and Caddy [citation:5]. **Consideration:** Browser components load from Mave’s hosted CDN by default, requiring internet access for the player.  
**Best for:** Teams wanting a modern, Elixir-based video platform with inspectable encoding pipelines and full control over storage and analytics.

### Hovod
**Stack:** Node.js / Fastify / React / FFmpeg / Redis / MySQL / S3 | **License:** Open Source (per Docker Hub)  
A self-hosted video platform positioned as an **open-source alternative to Mux**. Features include drag-drop upload or import from URL, **adaptive HLS transcoding** (360p to 4K, H.264), hardware-adaptive FFmpeg workers, S3-compatible storage (AWS, R2, B2, MinIO), and a built-in dashboard with video management and analytics [citation:2]. Optional AI processing includes Whisper transcription and auto-generated subtitles/chapters. Includes multi-tenancy with roles and API keys, optional Stripe billing, engagement features (comments, reactions), and webhooks. Deploys as an all-in-one Docker container including API, worker, dashboard, and embedded MariaDB/Redis — only requires S3-compatible storage [citation:2].  
**Best for:** Developers wanting a Mux-like self-hosted video infrastructure with transcoding, analytics, and optional monetization, deployable as a single container.

### AVideo
**Stack:** PHP / MySQL / FFmpeg / nginx-rtmp | **License:** Open Source (per Packagist)  
An open-source video platform with a website, encoder, and live server architecture. Features include video upload with conversion via FFmpeg, a video library with user accounts, and **live streaming** via RTMP ingest with HLS delivery [citation:11]. The architecture separates the Streamer (website/player), Encoder (video conversion), and Live server (broadcast ingest), allowing encoding workloads to run on separate servers. Supports S3/Backblaze B2 storage via plugins and Docker Compose deployment [citation:11].  
**Best for:** Organizations wanting a self-hosted video portal with both VOD and live streaming capabilities, accepting a PHP/MySQL stack.

### Owncast
**Stack:** Go / React | **License:** MIT  
An open-source, self-hosted, **single-user live video streaming and chat server** for running your own live streams similar to mainstream platforms [citation:4]. Offers complete ownership over content, interface, moderation, and audience. Compatible with any software using RTMP (OBS, Streamlabs, Restream). Includes built-in chat, federated engagement, and a web admin interface. Runs as a single Go service with no external dependencies. **Limitation:** Focused on live streaming only — not a VOD hosting platform.  
**Best for:** Individuals and organizations wanting full control over a live stream and chat experience without relying on commercial platforms.

### MediaMTX
**Stack:** Go | **License:** Open Source (per Go Packages)  
A ready-to-use, zero-dependency **real-time media server and media proxy** that publishes, reads, proxies, records, and plays back video and audio streams [citation:8]. Acts as a “media router” routing streams between protocols (SRT, WebRTC, RTSP, RTMP, HLS, MPEG-TS, RTP) with automatic conversion. Features include stream recording to disk (fMP4 or MPEG-TS), playback of recorded streams, JWT/HTTP authentication, Prometheus metrics, and hot reloading. Runs as a single executable on Linux, Windows, and macOS [citation:8]. **Note:** This is infrastructure, not a video portal — you build the frontend and management layer.  
**Best for:** Developers and platform engineers needing a reliable, protocol-agnostic media routing and recording layer for custom video applications.

### Tape
**Stack:** TypeScript / Next.js / Lens Protocol | **License:** AGPLv3  
An open-source video-sharing platform built on the Lens Protocol, with a frontend, embed player, API, and permissionless signup contracts [citation:9]. Positioned as a decentralized media-sharing application rather than a traditional video CMS. Still early-stage and tied to the Lens ecosystem.  
**Best for:** Developers interested in decentralized/social video platforms built on blockchain identity.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Live Streaming | Adaptive HLS | Self-Hosted | Best For |
|----------|---------|-------|----------------|--------------|-------------|----------|
| **Vimeo** | Proprietary | Cloud | ✅ (add-on) | ✅ | ❌ | User-friendly hosting + collaboration |
| **Brightcove** | Proprietary | Cloud | ✅ | ✅ | ❌ | Enterprise + OTT + marketing |
| **Wistia** | Proprietary | Cloud | ❌ | ✅ | ❌ | Video marketing + lead capture |
| **Vidyard** | Proprietary | Cloud | ❌ | ✅ | ❌ | Sales video + CRM integration |
| **Kaltura** | Proprietary | Cloud/on-prem | ✅ | ✅ | (Enterprise) | Enterprise video CMS |
| **Panopto** | Proprietary | Cloud/on-prem | ✅ | ✅ | (Enterprise) | Education + lecture capture |
| **Dacast** | Proprietary | Cloud | ✅ (live-first) | ✅ | ❌ | White-label live + VOD |
| **MediaCMS** | AGPL-3.0 | Python/Django | Limited | ✅ | ✅ | YouTube-like portal + transcoding |
| **Mave Core** | Open Source | Elixir/FFmpeg | ❌ | ✅ | ✅ | S3-native video platform |
| **Hovod** | Open Source | Node.js/FFmpeg | ❌ | ✅ (360p-4K) | ✅ | Mux alternative + optional billing |
| **AVideo** | Open Source | PHP/nginx-rtmp | ✅ (RTMP) | ✅ | ✅ | VOD + live streaming portal |
| **Owncast** | MIT | Go | ✅ (live-only) | ❌ | ✅ | Single-user live streaming + chat |
| **MediaMTX** | Open Source | Go | ✅ (multi-protocol) | (Routing) | ✅ | Media routing + recording infrastructure |
| **Tape** | AGPLv3 | TypeScript/Lens | ❌ | (Check) | ✅ | Decentralized video sharing |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Video Hosting or Streaming platform that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
