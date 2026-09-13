<div align="center">
  <h1>Mussie Aklilu Gebrearegawi</h1>
  <p><strong>Software Engineer</strong> · Munich, Germany 🇩🇪</p>
</div>

---

I take problems end to end — the data model underneath, the API in the middle, and
the interface people actually touch. I'd rather ship something whole and slightly
boring than something clever with a gap in it.

My depth is in TypeScript and the web, across React, Angular and Vue. But I don't
hand off at the API boundary: schema design, access control, background jobs and
real-time pipelines are part of the same problem, and owning them beats coordinating
around them.

What that looks like in practice — deriving state instead of storing it so the UI
can't disagree with its data, putting authorization in the database rather than in
an `if` statement someone will forget, and splitting long-running work so a timeout
costs a retry instead of a corrupted result.

I care more about whether a decision holds up in six months than whether it's
fashionable.

---

## What I work with

![TypeScript](https://img.shields.io/badge/TypeScript-%23007acc.svg?style=for-the-badge&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)
![Angular](https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=for-the-badge&logo=supabase&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-black?style=for-the-badge&logo=next.js&logoColor=white)

Also build in **Python**, **Go** and **Java**.

<details>
<summary>Fuller stack</summary>

**Frontend** — Vue, Nuxt, Preact, Electron, Tailwind, SCSS, Material UI, Storybook
**State** — Redux Toolkit, NgRx, Zustand, Pinia, TanStack Query
**Backend & data** — Express, NestJS, Edge Functions, MongoDB, MySQL, row-level security, pg_cron
**Testing** — Vitest, Jest, Playwright, React Testing Library
**Build & infra** — Vite, Webpack, Kubernetes, AWS, GitHub Actions, Vercel
**APIs & realtime** — REST, GraphQL, WebSockets, Auth0
**Visualization** — D3.js, Three.js, WebGL

</details>

---

## Selected work

Two systems I built and deployed end to end — schema, backend, interface and
infrastructure. Included less as a portfolio than as a sample of how I make
technical decisions and what I consider finished.

### SignalScope · [live demo](https://signal-scope-gamma.vercel.app/)

A real-time service map for distributed systems — renders a live event stream as an
interactive topology rather than as logs or a static dashboard.

- **Two stores, because they answer different questions.** Raw events for the live
  view, one-second rollups for history. Scrubbing back an hour over raw rows is a
  full scan per frame; over rollups it's a few thousand pre-summed rows
- **Rollups are written in the same transaction as the insert**, by a single
  statement-level trigger — so a metric is never stale relative to its events and
  there's no rollup job that can fall behind
- **Live updates fan out as one broadcast per batch**, not one message per row —
  at a few hundred events a second the per-row alternative is a firehose the client
  spends its frame budget unpacking
- Service health is *derived*, never set imperatively: a pure function of the events
  in a rolling window, so the visualization can't disagree with its data. Replay fell
  out of that for free — one hook swap, not a parallel rendering path
- Topology is hand-written SVG; no graph library

### Composer Studio · [live demo](https://composer-studio-plum.vercel.app/)

A drag-and-drop email builder — compose, preview, export cross-client HTML, and send.

- **The send pipeline splits into queue and drain**, so a large campaign survives a
  function timeout; a unique constraint on (mail, recipient) means a retry can't
  double-send
- **Authorization lives in the database**, not the application — row-level security
  on every table, with an explicit grant model rather than relying on defaults
- **Engagement stats are derived from immutable event rows**, so a number can't drift
  from what produced it. Opens count unique recipients, and rates divide by delivered
  rather than by sent
- A deeply nested document tree (blocks → columns → elements) as a typed discriminated
  union, mutated from a dozen places with snapshot-based undo/redo
- Email-safe HTML generator — nested tables, inlined styles — with an importer that
  reconstructs the document back out of that markup

---

## Connect

<p align="left">
  <a href="mailto:mussieaz126@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-D14836?style=flat-square&logo=gmail&logoColor=white" />
  </a>
  <a href="https://www.linkedin.com/in/mussie-gebrearegawi-25419a17b/">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white" />
  </a>
</p>
