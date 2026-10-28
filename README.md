<h1 align="center">Rupesh Chidupudi</h1>

<p align="center">
  <b>Building at <a href="https://datenwork.in">Datenwork</a></b> · Edge-to-cloud systems · Hyderabad, India<br/>
  <sub>Also contributing to engineering work across other organisations</sub>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/rupeshchidupudi/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="mailto:chrupesh2425@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=flat-square&logo=gmail&logoColor=white" alt="Email"/></a>
  <a href="https://datenwork.in"><img src="https://img.shields.io/badge/datenwork.in-111111?style=flat-square&logo=googlechrome&logoColor=white" alt="Website"/></a>
</p>

---

At Datenwork I'm building a connected in-vehicle advertising network. I design and run the platform
behind its fleet of GPS- and LTE-connected screens, end to end:
the device OS and agent, the ingest API, the real-time streaming layer, the data lake, and the cloud
infrastructure it all runs on. My focus is on systems that are reliable on bad networks, cheap at fleet
scale, and simple enough for a small team to operate.

### What I'm building

**Fleet telemetry & real-time tracking**
- 1 Hz GPS, health and proof-of-play telemetry from edge devices. Ingest is **idempotent** (devices retry
  after connectivity gaps) and acknowledged only once the write is durable.
- A **Go server-sent-events relay** that fans live positions out to dashboards, with HMAC-signed,
  role-scoped tokens (operators see the fleet; advertisers see only their booked screens).
- A history pipeline: **Kinesis Data Firehose → Parquet on S3 → Glue / Athena**, using partition
  projection and deduplicated views. Earlier it ran on Pub/Sub → BigQuery; I migrated it with row
  counts checked against the source.

**Multi-tenant backend**
- A TypeScript API (**Fastify + Zod**, with shared schemas as the single contract between API, web and devices).
- **PostgreSQL row-level security** (Supabase) enforces tenant isolation in the database, not in handlers.
- Ad-serving manifests with approval gating, scheduling and dayparting. Media goes straight to object
  storage through presigned URLs (Cloudflare R2), never through the API.

**Edge devices & networking**
- Linux devices (Raspberry Pi; Rockchip RK3566 tablets next) on Alpine/OpenRC, with LTE modems and
  GNSS, and a device agent written in Go.
- A self-hosted **Headscale** (WireGuard/Tailscale control plane) mesh for remote access to every
  device, plus centralised device logging.

**Cloud & cost engineering**
- Led the **GCP → AWS migration**: idempotent infrastructure scripts, **keyless CI/CD** (GitHub OIDC →
  ECR → SSM Run Command, no SSH, no stored credentials), arm64 (Graviton) containers, and secrets in
  SSM Parameter Store.
- Brought write and egress cost down at fleet scale: batching database writes across all devices,
  snapshot-cached manifests, and record packing for streaming ingest.

### Stack

<p>
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white"/>
  <img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white"/>
  <img src="https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white"/>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB"/>
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white"/>
  <img src="https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white"/>
  <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white"/>
  <img src="https://img.shields.io/badge/Google_Cloud-4285F4?style=flat-square&logo=googlecloud&logoColor=white"/>
  <img src="https://img.shields.io/badge/Cloudflare-F38020?style=flat-square&logo=cloudflare&logoColor=white"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/>
  <img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black"/>
  <img src="https://img.shields.io/badge/WireGuard-88171A?style=flat-square&logo=wireguard&logoColor=white"/>
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white"/>
</p>

**Languages:** TypeScript, Go, Python, SQL, Java<br/>
**Data:** PostgreSQL, Athena / Parquet, BigQuery, Redis, MongoDB<br/>
**Infra:** AWS (EC2 Graviton, S3, Firehose, Glue, Athena, ECR, SSM, IAM), GCP (Cloud Run, Pub/Sub, BigQuery), Cloudflare (Pages, R2, DNS)

### Engineering principles I work by

- **Correct under retries.** Network edges fail, so every write path is idempotent and acks only after durability.
- **Isolation in the data layer.** Tenancy is enforced by the database itself, so a handler bug can't leak data.
- **Keyless and least-privilege.** Short-lived OIDC credentials and scoped IAM, no long-lived secrets in CI.
- **Measure before and after.** Migrations are verified against the source (row counts, deduplicated counts, side-by-side outputs).

### Earlier work

Full-stack products for clients (restaurant operations, healthcare and campus management systems),
plus ML experiments in network security (DDoS detection) and energy forecasting.

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=chidupudi&layout=compact&hide_border=true&langs_count=6" height="150"/>
</p>
