<div align="center">
  <h1>Mussie Aklilu Gebrearegawi</h1>
  <p><strong>Software Engineer</strong> · Munich, Germany 🇩🇪</p>
</div>

---

I build web applications end to end — mostly TypeScript on the frontend, and the
backend behind it when that's what the problem needs.

Most of my work is frontend architecture: component systems that stay coherent as
they grow, state that's derived rather than duplicated, and interfaces that stay
responsive under real data volume. I'm equally comfortable owning what sits behind
them — schema design, row-level security, and the API surface in between.

I work across React, Angular and Vue rather than defending one of them, and I care
more about whether a decision holds up in six months than whether it's fashionable.

---

## What I work with

![TypeScript](https://img.shields.io/badge/TypeScript-%23007acc.svg?style=for-the-badge&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)
![Next.js](https://img.shields.io/badge/Next.js-black?style=for-the-badge&logo=next.js&logoColor=white)
![Angular](https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![Vue.js](https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white)

Also work in **Python**, **Go** and **Java**.

<details>
<summary>Fuller stack</summary>

**Frontend** — Nuxt, Preact, Electron, SCSS, Material UI, Storybook
**State** — Redux Toolkit, NgRx, Zustand, Pinia, TanStack Query
**Backend & data** — Express, NestJS, Supabase, MongoDB, MySQL
**Testing** — Vitest, Jest, Playwright, React Testing Library
**Build & infra** — Vite, Webpack, Docker, Kubernetes, AWS, GitHub Actions, Vercel
**APIs** — REST, GraphQL, WebSockets, Auth0
**Visualization** — D3.js, Three.js, WebGL

</details>

---

## Selected work

Two recent builds, included less as a portfolio than as a sample of how I make
technical decisions and what I consider finished.

### SignalScope · [live demo](https://signal-scope-gamma.vercel.app/)

A real-time service map for distributed systems — renders a live event stream as an
interactive topology rather than as logs or a static dashboard.

- Service health is **derived**, never set imperatively: status is a pure function of
  the events in a rolling window, so the visualization can't disagree with its data
- Replay falls out of that for free — pausing and scrubbing backwards required
  swapping a single hook, not building a parallel rendering path
- Topology is hand-written SVG; no graph library
- Postgres backend keeps raw events for the live view and one-second rollups for
  history, both written in the same transaction as the insert
- Live updates fan out as **one broadcast per batch**, not one message per row

### Composer Studio · [live demo](https://composer-studio-plum.vercel.app/)

A drag-and-drop email builder — compose, preview, export cross-client HTML, and send.

- A deeply nested document tree (blocks → columns → elements) modelled as a typed
  discriminated union, mutated from a dozen places with snapshot-based undo/redo
- Email-safe HTML generator — nested tables, inlined styles — paired with an importer
  that reconstructs the document from that markup
- The send pipeline splits into *queue* and *drain*, so a large campaign survives a
  function timeout and a retry can't double-send
- Per-recipient open/click attribution behind signed links, with unsubscribes
  suppressed permanently across future sends

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
