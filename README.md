<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://www.boumlikbrahim.com/White-BB-BrandLogo.png" />
  <source media="(prefers-color-scheme: light)" srcset="https://www.boumlikbrahim.com/Black-BB-BrandLogo.png" />
  <img src="https://www.boumlikbrahim.com/White-BB-BrandLogo.png" alt="Brahim Boumlik Logo" height="80" />
</picture>

# Brahim Boumlik

*I wrote the bootloader, the heap allocator, and the interrupt handlers.*
*I also lead the team shipping AI-powered SaaS to production on Azure.*
*Neither is a hobby.*

[![Portfolio](https://img.shields.io/badge/Portfolio-boumlikbrahim.com-black?style=for-the-badge&logo=vercel&logoColor=white)](https://www.boumlikbrahim.com)
[![Blog](https://img.shields.io/badge/Blog-boumlikbrahim.com/blog-black?style=for-the-badge&logo=hashnode&logoColor=white)](https://www.boumlikbrahim.com/blog)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Brahim_Boumlik-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/brahim-boumlik-4159b722b/)
[![GitHub](https://img.shields.io/badge/GitHub-Boumlik--Brahim-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Boumlik-Brahim)
[![Email](https://img.shields.io/badge/Email-contact@boumlikbrahim.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:contact@boumlikbrahim.com)

<br>

[![bbrahim's 42 stats](https://badge.mediaplus.ma/black/bbrahim)](https://github.com/oakoudad/badge42)

</div>

---

Full-stack **Technical Lead** with 2+ years shipping distributed systems and cloud-native microservices on Azure — 5 engineers, 24+ sprints, 99.8% uptime, GPT-4o in production (Paris, Remote).
Graduate of **1337 Coding School / 42 Network** (RNCP7 · EQF Level 7 · Master's equivalent). I work from kernel memory management up to cloud architecture — the low-level work shapes every high-level decision.

---

## Currently Shipping

- Architecting a multi-service backend on Azure Container Apps: NestJS microservices over TCP/RabbitMQ, Django AI service with GPT-4o, Next.js frontend — all in a Turborepo monorepo
- Managing CI/CD pipelines, cloud infrastructure, and cross-team deployments for a distributed engineering team across 2 countries
- Iterating on AI-powered product features and real-time analytics shipped to paying B2B customers at [app.fygurs.com](https://app.fygurs.com)

---

## Selected Projects

### Fygurs — AI-Powered Product Management SaaS *(Production · Technical Lead)*

**The problem:** Coordinate 5 engineers across 2 countries in a monorepo where multiple services must deploy independently — without a 2-hour pipeline blocking every release — and integrate AI without coupling it to the core backend.

**How I solved it:** Turborepo monorepo with service-level Docker builds and GitHub Actions pipelines (caching + parallelization) — pipeline from 2 hours to 15 minutes. Azure Container Apps for isolated, independently scalable services. NestJS microservices over TCP for synchronous calls, RabbitMQ for async events. GPT-4o in a dedicated Django service — the AI layer is a service boundary, not a library import. PostgreSQL Flexible Server + Blob Storage, 99.8% uptime.

**What it proved:** Monorepos succeed in production when the build system is a first-class engineering problem. AI belongs behind a service interface, not inline in business logic.

→ [fygurs.com](https://fygurs.com) · [app.fygurs.com](https://app.fygurs.com)

---

### ft_transcendence — Real-Time Multiplayer Platform

**The problem:** Real-time game state synchronization across concurrent users where frame inconsistency feels like physics breaking — while simultaneously building auth, chat, and leaderboards.

**How I solved it:** Server-authoritative game loop over Socket.io — the client renders what the server says, not what it guesses. OAuth 2.0 authentication, live chat with channel management, real-time leaderboard backed by PostgreSQL with Prisma. Entire stack containerized: TypeScript, Next.js, NestJS, Docker.

**What it proved:** Real-time multiplayer is a state ownership problem before it's a WebSocket problem. If the client has any authority over game state, you've already lost.

→ [github.com/Boumlik-Brahim/ft_transcendence](https://github.com/Boumlik-Brahim/ft_transcendence)

---

### KFS-1 & KFS-2 — 32-bit Kernel in C and Assembly

**The problem:** Build a functioning OS kernel with no standard library, no OS primitives, no abstractions. Every layer must be correct before the next one can exist.

**How I solved it:** GRUB bootloader → VGA display driver → GDT/IDT configuration → ISR/IRQ interrupt handling → keyboard driver → memory paging → heap allocator → PIT/RTC timing. Each component hand-written in C and x86 Assembly. No shortcuts, no libraries.

**What it proved:** Writing a heap allocator changes how you read memory profiler output. Implementing interrupt handling reframes every async I/O system you'll ever build. I debug differently now.

---

### minishell — Unix Shell in C

**The problem:** Rebuild a POSIX-compliant Unix shell from scratch — the program every developer uses daily but almost nobody understands at the system level.

**How I solved it:** Lexer, parser, and execution engine in C. Pipes, redirections, here-docs, SIGINT/SIGQUIT signal handling, process management (fork/execve/wait), environment variable expansion, and all required built-in commands.

**What it proved:** The shell is the most honest introduction to how an OS runs processes. After this, system calls stopped being magic.

---

### Snow-Crash · Rainfall · Override — Binary Exploitation CTFs

**The problem:** 14 escalating levels — buffer overflows, reverse engineering ELF binaries with GDB, privilege escalation via SUID, return-oriented programming — no documentation, no hints.

**How I solved it:** A repeatable methodology: disassemble, map the memory layout, identify the attack vector, craft and test the payload. Privilege escalation from user to root across multiple binary protection schemes and architectures.

**What it proved:** I write backend systems with a working mental model of how they look from the attacker's side. It changes what gets flagged in code review and what I refuse to ship without hardening.

---

### ft_shield — Educational Malware in C and Assembly *(42 Security Project)*

**The problem:** Understand offensive techniques — trojans, polymorphic viruses, process injection — at the implementation level, not the conceptual one.

**How I solved it:** Built a set of educational malware samples: backdoor with remote shell, self-replicating polymorphic virus with code mutation, and a process injector using ptrace. Written in C and x86 Assembly within a controlled, air-gapped environment.

**What it proved:** You cannot write secure systems without understanding how they break. This project made threat modeling concrete, not theoretical.

---

### Inception-of-Things & Cloud-1 — Kubernetes GitOps from Scratch

**The problem:** Stand up a production-grade, multi-node Kubernetes environment — GitOps-driven with real ingress routing — entirely from local VMs, no managed cloud.

**How I solved it:** K3s cluster on Vagrant VMs, K3d for local dev parity. Argo CD as the GitOps controller — git is the authoritative source for cluster state, not kubectl commands. Traefik ingress for routing. Every infrastructure change is a PR.

**What it proved:** Infrastructure that isn't in version control isn't infrastructure — it's technical debt waiting to manifest. This is now the mental model behind every cloud environment I architect.

---

## Tech Stack

<div align="center">

**Languages**

[![Languages](https://skillicons.dev/icons?i=ts,js,python,c,cpp,php&theme=dark&perline=6)](https://skillicons.dev)

**Backend**

[![Backend](https://skillicons.dev/icons?i=nestjs,nodejs,django,laravel,rabbitmq,redis&theme=dark&perline=6)](https://skillicons.dev)

**Frontend**

[![Frontend](https://skillicons.dev/icons?i=nextjs,react,tailwind&theme=dark&perline=6)](https://skillicons.dev)

**Cloud & DevOps**

[![DevOps](https://skillicons.dev/icons?i=azure,docker,kubernetes,githubactions,nginx,linux&theme=dark&perline=6)](https://skillicons.dev)

</div>

<div align="center">

**Databases**

[![Databases](https://skillicons.dev/icons?i=postgres,prisma,mysql,mariadb&theme=dark&perline=6)](https://skillicons.dev)

</div>

---

## GitHub Stats

<div align="center">

<img width="100%" src="https://streak-stats.demolab.com/?user=Boumlik-Brahim&theme=tokyonight&hide_border=true&border_radius=12&fire=bf91f3&ring=70a5fd&currStreakLabel=70a5fd&sideLabels=bf91f3&dates=a9b1d6&stroke=1a1b27" />

</div>

<br>

<div align="center">

<img height="195" src="https://github-readme-stats.vercel.app/api?username=Boumlik-Brahim&theme=tokyonight&hide_border=true&include_all_commits=true&count_private=true&show_icons=true&icon_color=70a5fd&rank_icon=github&border_radius=12&card_width=450" />
<img height="195" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Boumlik-Brahim&theme=tokyonight&hide_border=true&layout=donut-vertical&langs_count=7&border_radius=12&card_width=330" />

</div>

<br>

<div align="center">

<img width="100%" src="https://github-readme-activity-graph.vercel.app/graph?username=Boumlik-Brahim&theme=tokyo-night&hide_border=true&area=true&custom_title=Contribution%20Graph&color=70a5fd&line=70a5fd&point=bf91f3&area_color=1a1b27&radius=6" />

</div>

---

## 42 Cursus

<div align="center">

<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/common_core.webp" height="90" />

</div>

<div align="center">

<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/libft_bonus.webp" height="62" />
<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/get_next_line_bonus.webp" height="62" />
<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/ft_printf_bonus.webp" height="62" />
<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/born2beroot_bonus.webp" height="62" />
<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/so_long_bonus.webp" height="62" />
<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/minitalk_bonus.webp" height="62" />
<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/push_swap_bonus.webp" height="62" />
<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/philosophers_bonus.webp" height="62" />
<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/minishell.webp" height="62" />
<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/netpractice.webp" height="62" />
<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/cpp.webp" height="62" />
<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/cub3d_bonus.webp" height="62" />
<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/inception_bonus.webp" height="62" />
<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/ft_irc_bonus.webp" height="62" />
<img src="https://github.com/leogaudin/42_project_badges/raw/main/badges/ft_transcendence.webp" height="62" />

</div>

---

<div align="center">

Building distributed systems from Casablanca, Morocco — open to senior engineering and technical leadership roles worldwide.

</div>
