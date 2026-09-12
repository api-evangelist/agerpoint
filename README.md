# Agerpoint

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

Agerpoint is a spatial-intelligence company in Research Triangle Park, North Carolina that turns
real-world field data into AI-derived crop, tree and land measurements. Its Capture mobile app builds
full-resolution 3D digital twins of plants from a smartphone or tablet video, and Agerpoint Cloud — a
spatial data management and analytics platform — fuses those captures with LiDAR, drone imagery,
satellite data, sensors and equipment telemetry to derive plant metrics for yield estimation, disease
detection, carbon sequestration and biodiversity assessment.

## API status

Agerpoint runs a live REST API at `https://cloudapi.agerpoint.com`, secured by OAuth 2.0 bearer tokens
from the `agerpoint.us.auth0.com` tenant. It is a **customer-only surface**: it powers the first-party
console at `cloud.agerpoint.com` and the Capture mobile apps, and Agerpoint publishes no developer
portal, no API reference, and no machine-readable contract of any kind for it. Unauthenticated requests
answer `401` with `WWW-Authenticate: Bearer`.

Probed 2026-09-12 and **not** found at any public URL: OpenAPI/Swagger, GraphQL SDL, WSDL, AsyncAPI,
Postman collection, MCP server, A2A agent card, `llms.txt`, `security.txt`, `/.well-known/api-catalog`,
pricing page, status page, changelog, deprecation policy, or an SDK on any package registry.

Two OGC surfaces exist but are gated: an OGC Web Map Service at `/api/maps/wms` (HTTP 401) and a
TiTiler 1.2.0 raster-tile service at `tiles.agerpoint.com` serving the WebMercatorQuad tile matrix set
over Cloud Optimized GeoTIFF (HTTP 403). No OGC capabilities document was retrievable, so none is
recorded here.

One decay signal worth reporting to Agerpoint: `api.agerpoint.com` is a **dangling CNAME** to
`agerapi.azurewebsites.net`, an Azure App Service that no longer resolves. That is both a stale record
and a subdomain-takeover exposure.

## What is in this repository

| Path | What it holds |
|---|---|
| `apis.yml` | The APIs.json profile — identity, the one API entry, and every artifact pointer |
| `well-known/` | Probe index for every host, plus the three real documents the Auth0 tenant serves |
| `authentication/` | The OAuth 2.0 / OIDC profile, read from the authorization server's own discovery document |
| `scopes/` | The only scope list Agerpoint publishes (OIDC identity scopes); API scopes are not published |
| `conventions/` | REST conventions observed from the first-party console — pagination, jobs, idempotency, reversibility |
| `conformance/` | Standards conformance established by probe, including the two gated OGC surfaces |
| `security/` | TLS/HSTS/DNSSEC/CAA/SPF/DMARC probe results |
| `packages/` | Registry search results (zero SDKs) and the two Capture mobile-app distributions |
| `plans/`, `rate-limits/`, `lifecycle/` | Recorded absences — pricing, limits and lifecycle policy are unpublished |
| `llms/` | A generated `llms.txt` describing what an agent can and cannot reach |
