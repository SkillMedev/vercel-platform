# Vercel Deployment & Platform

**A curated, opinionated path for shipping a Next.js app on Vercel - deploys, env, AI Gateway, rendering & caching, firewall, and performance.** — built in-house by [Skill&nbsp;Me](https://skillme.dev/?utm_source=github&utm_medium=readme&utm_campaign=pack-vercel-platform).

Sequences the modern Vercel surface into one ship-a-Next.js-app workflow rather than a pile of disconnected tips. Run the deploy pipeline (preview→production, rollbacks, rolling releases, CI), manage environment variables and OIDC across environments, route every model call through the AI Gateway, pick the right rendering and caching strategy on Fluid Compute (ISR/PPR, Next.js Cache Components, runtime cache), lock the app down with the WAF and BotID, and tune Core Web Vitals. Authored against current Vercel docs (Edge Functions are deprecated, Node 24 default, 300s timeouts, vercel.ts config) and bundled with the catalog's Next.js App Router and Web Performance skills.

## Install

- **Claude, ChatGPT, Codex, Cursor (connector):** [install the whole pack from skillme.dev](https://skillme.dev/pack/vercel-platform?utm_source=github&utm_medium=readme&utm_campaign=pack-vercel-platform) — one connection, then ask for any skill by name.
- **As files for Codex, Cursor, or Claude Code:** `npx @skillme/cli add vercel-deploy-pipeline vercel-env-management vercel-ai-gateway vercel-edge-and-isr vercel-firewall-and-botid next-on-vercel-perf nextjs-app-router web-performance --target all`
- **With the skills CLI:** `npx skills add SkillMedev/vercel-platform`
- **Manually:** copy any `skills/<slug>/SKILL.md` into `.agents/skills/`, `.cursor/skills/`, or `.claude/skills/`.

⭐ **If this is useful, star the repo** — it's how we gauge what to build next.

## Skills in this pack

- **[Vercel Deploy Pipeline](skills/vercel-deploy-pipeline/SKILL.md)** — Ship a Next.js app to Vercel the production way: promote a tested preview to production, instant-rollback a bad release, build once with --prebuilt, run a staged/canary rollout with Rolling Releases (GA), and wire the deploy into CI.
- **[Vercel Env Management](skills/vercel-env-management/SKILL.md)** — Manage environment variables across Vercel environments and keep local .env in sync - vercel env pull/add/rm/ls, per-environment values (development/preview/production + custom), sensitive secrets, OIDC tokens for keyless cloud access, and the NEXT_PUBLIC build-time inlining gotcha.
- **[Vercel AI Gateway](skills/vercel-ai-gateway/SKILL.md)** — Route every LLM call through one unified API on Vercel - plain "provider/model" strings via the AI SDK, automatic provider routing and model fallbacks, observability and per-key cost tracking, and zero data retention.
- **[Vercel Rendering and Caching](skills/vercel-edge-and-isr/SKILL.md)** — Choose a rendering, runtime, and caching strategy on Vercel - Fluid Compute as the default runtime (Edge Functions are deprecated), ISR/PPR, Next.js 16 Cache Components ('use cache', cacheLife, cacheTag, updateTag, revalidateTag), and the Vercel Runtime Cache API (getCache, expireTag, invalidateByTag) with tag-based invalidation.
- **[Vercel Firewall and BotID](skills/vercel-firewall-and-botid/SKILL.md)** — Harden a Vercel app at the platform edge - the Vercel WAF (custom rules, IP blocking, managed rulesets like OWASP CRS + bot_protection + ai_bots, rate limiting), Attack Challenge Mode, system bypass rules, automatic DDoS mitigation, and BotID bot verification on sensitive routes.
- **[Next on Vercel Performance](skills/next-on-vercel-perf/SKILL.md)** — Diagnose and fix Core Web Vitals and page performance of a Next.js app on Vercel - measurement-first.
- **[Next.js App Router](skills/nextjs-app-router/SKILL.md)** — Builds and reviews Next.js App Router code - server/client component boundaries, data fetching, caching and revalidation choices, streaming with Suspense, and Server Action mutations - and delivers routes where every dynamic-vs-cached decision is explicit.
- **[Web Performance](skills/web-performance/SKILL.md)** — Diagnoses and fixes Core Web Vitals - LCP, INP, and CLS - through an ordered audit procedure with concrete code-level changes for images, fonts, JavaScript, and third-party scripts.

## License

MIT — see [LICENSE](LICENSE). Skills are portable `SKILL.md` files; the canonical
copies live in the [Skill&nbsp;Me catalog](https://skillme.dev/browse?utm_source=github&utm_medium=readme&utm_campaign=pack-vercel-platform).
