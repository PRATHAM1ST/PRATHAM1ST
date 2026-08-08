<h1 align="center">Pratham Chudasama</h1>

<p align="center">
  Full-stack engineer. I build things that ship — web, mobile, desktop, and the hardware they talk to.
</p>

<p align="center">
  <a href="https://prathamchudasama.com"><img src="https://img.shields.io/badge/Portfolio-prathamchudasama.com-0b0b0b?style=for-the-badge&logo=vercel&logoColor=white" alt="Portfolio" /></a>
  <a href="https://twitter.com/Pratham1st2002"><img src="https://img.shields.io/badge/X-@Pratham1st2002-1d9bf0?style=for-the-badge&logo=x&logoColor=white" alt="X" /></a>
</p>

<p align="center"><sub>Chain Labs &nbsp;·&nbsp; India</sub></p>

---

### What I actually do

Most of my work is full-stack TypeScript — Next.js on the front, Postgres behind it. But the projects I like
best are the ones that leave the browser: an ESP32 publishing QR scans over MQTT into an Electron app, a
.NET MAUI catalogue that has to stay useful with no signal, a set of Solidity contracts that have to be
deployed in exactly the right order or they deadlock.

I care about the boring parts — idempotent cron jobs, debounced sensor reads, not trusting the client for a price.

---

### Selected work

**Gym CRM** &nbsp;·&nbsp; `Electron` `Vue 3` `SQLite` `MQTT` `ESP32`
A local-first gym management desktop app — members, QR check-in, attendance, finance, GST receipts. The Electron
main process hosts its own MQTT broker and SQLite database over typed IPC, so there's no server to run. A companion
ESP32-S runs camera capture on one core and QR decoding on the other, publishing check-ins over MQTT.
<sub>**Hard part:** the firmware had three FreeRTOS tasks sharing one WebSocket, non-atomic counters across cores, and a null-deref in the decode loop. Fixed by giving a single task sole ownership of the socket.</sub>

**DeBruycker Charolais** &nbsp;·&nbsp; `.NET MAUI` `C#` `Bun` `SQLite`
An iOS + Android companion app for a live cattle auction — browse the catalogue, filter on pedigree metrics, save
favourites — backed by a Bun service that ingests auction webhooks and serves them over a versioned REST API.
Offline-first: everything caches to on-device SQLite.
<sub>**Hard part:** favourites are client state living in server-synced rows. The sync had to deliberately re-apply them instead of overwriting on every refresh.</sub>

**ProofMarket** &nbsp;·&nbsp; `Solidity` `Hardhat` `Viem` `Next.js`
A creator-backing protocol on Sepolia — capped ERC20 with votes, ERC721 supporter badges with royalties, a
royalty-aware marketplace, time-based staking, and full Governor + Timelock governance across eight contracts.
<sub>**Hard part:** those eight contracts grant each other roles in a cycle-prone order. Ignition's dependency graph made it explicit at module-definition time — a circular reference deadlocks the deploy instead of failing on a live network.</sub>

**CQRC** &nbsp;·&nbsp; `Next.js` `Upstash` `RAG` — [live](https://cqrc.vercel.app) · [code](https://github.com/PRATHAM1ST/cqrc)
A support chatbot grounded in whatever you upload — PDF, DOCX, XLSX, or hand-written Q&A pairs. Retrieval is
hand-rolled BM25 over chunks in Redis, no embedding model and no vector DB. It refuses to answer outside the corpus.
<sub>**Hard part:** BM25 recomputes IDF per query term across every chunk, so the Redis pipeline fetches eagerly. Fine for a controlled vocabulary; the trade is that synonyms are invisible to the scorer.</sub>

**RG Games** &nbsp;·&nbsp; `Next.js` `Drizzle` `Supabase` — [live](https://rg-games.vercel.app) · [code](https://github.com/PRATHAM1ST/rg-games)
Gaming-events booking — browse, reserve, pay. Admins manage events, sessions, players, and leaderboards.
<sub>**Hard part:** two payment providers behind one interface, but their webhook signature schemes are different enough to need separate handlers. Free events bypass order creation entirely and confirm server-side from the DB price — never the client's.</sub>

**IdLocker** &nbsp;·&nbsp; `React Native` `Expo`
A fully offline vault for cards, government IDs, and credentials. Biometric unlock, auto-lock on background,
screen capture blocked, no network calls at all.
<sub>**Hard part:** `expo-secure-store` caps each key at 2 KB, so a vault has to be chunked across multiple entries and reassembled — ordering and partial-write failures are where the corruption lives.</sub>

<sub>More, with writeups → **[prathamchudasama.com](https://prathamchudasama.com)**</sub>

---

### Stack

**Languages**

<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/typescript/typescript-original.svg" alt="TypeScript" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg" alt="JavaScript" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg" alt="Python" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/csharp/csharp-original.svg" alt="C#" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/cplusplus/cplusplus-original.svg" alt="C++" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/solidity/363636/f0f0f0" alt="Solidity" width="42" height="42" />

**Frontend**

<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original.svg" alt="React" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/nextdotjs/000000/ffffff" alt="Next.js" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg" alt="Vue" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/tailwindcss/tailwindcss-original.svg" alt="Tailwind CSS" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/shadcnui/000000/ffffff" alt="shadcn/ui" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/radixui/000000/ffffff" alt="Radix UI" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/framer/0055FF" alt="Framer Motion" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/threedotjs/000000/ffffff" alt="Three.js" width="42" height="42" />

**Backend & data**

<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nodejs/nodejs-original.svg" alt="Node.js" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/express/000000/ffffff" alt="Express" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/bun/FBF0DF/FBF0DF" alt="Bun" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-original.svg" alt="PostgreSQL" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mongodb/mongodb-original.svg" alt="MongoDB" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/sqlite/sqlite-original.svg" alt="SQLite" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/prisma/prisma-original.svg" alt="Prisma" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/drizzle/C5F74F" alt="Drizzle ORM" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/supabase/supabase-original.svg" alt="Supabase" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/graphql/graphql-plain.svg" alt="GraphQL" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/redis/FF4438" alt="Redis / Upstash" width="42" height="42" />

**AI**

<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/pytorch/pytorch-original.svg" alt="PyTorch" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/huggingface/FFD21E" alt="Hugging Face" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/vercel/000000/ffffff" alt="Vercel AI SDK" width="42" height="42" />

**Mobile, desktop & embedded**

<img src="https://cdn.simpleicons.org/expo/000020/ffffff" alt="Expo" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/dotnet/512BD4" alt=".NET MAUI" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/electron/electron-original.svg" alt="Electron" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/arduino/arduino-original.svg" alt="Arduino" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/espressif/E7352C" alt="ESP32" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/mqtt/660066/8a2be2" alt="MQTT" width="42" height="42" />

**Tooling & platform**

<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/git/git-original.svg" alt="Git" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vitejs/vitejs-original.svg" alt="Vite" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/vercel/000000/ffffff" alt="Vercel" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/railway/000000/ffffff" alt="Railway" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/firebase/firebase-plain.svg" alt="Firebase" width="42" height="42" />&nbsp;
<img src="https://cdn.simpleicons.org/sanity/F03E2F" alt="Sanity" width="42" height="42" />&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/figma/figma-original.svg" alt="Figma" width="42" height="42" />

---

<p align="center">
  <sub>Open to interesting problems — <a href="https://prathamchudasama.com">prathamchudasama.com</a></sub>
</p>
