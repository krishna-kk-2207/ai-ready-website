# Make your website readable for AI agents

Your website looks good but gets little traffic? Two kinds of visitors come to it: **people** and **AI agents** (ChatGPT, Claude and others). People see your design. AI agents read the code underneath, and menus, pop-ups and scripts get in the way of your actual content.

The fix: **one link, two versions**. A nice page for people, a clean plain-text (Markdown) page for AI. Your site checks who is asking and sends the right one.

This page collects the free tools mentioned in the reel. Every repo, command and number below was checked against the project's own README on 20-11-2026.

## The 3 tools from the reel

| # | Tool | What it does (from its README) | Install |
|---|------|--------------------------------|---------|
| 1 | [BartWaardenburg/isagentready-skills](https://github.com/BartWaardenburg/isagentready-skills) | A *skill*: instructions your AI coding agent (Claude Code, Cursor, Codex and others) can follow. It has fix steps for every problem the [isagentready.com](https://isagentready.com) scanner reports: robots.txt, structured data (JSON-LD), semantic HTML, agent protocols and security headers. MIT licence. | `npx skills add bartwaardenburg/isagentready-skills` |
| 2 | [@vercel/agent-readability](https://www.npmjs.com/package/@vercel/agent-readability) | **The part that sends the right version to the right visitor.** It detects AI agents and serves them a clean Markdown version, with adapters for Next.js, SvelteKit, Nuxt and Vercel. Follows Vercel's [Agent Readability Spec](https://vercel.com/kb/guide/agent-readability-spec). MIT licence. | `npm install @vercel/agent-readability` |
| 3 | [iannuttall/seo](https://github.com/iannuttall/seo) | Gives your agent your **real** Google Search Console, Analytics and Bing numbers, plus a site crawl that checks what AI agents can read. Free, open source (Apache-2.0). | `claude mcp add --transport http seoskill https://seoskill.dev/mcp` (Claude Code) |

Free check of your site with tool #2, nothing to install:

```bash
npx @vercel/agent-readability audit https://your-site.com
```

### Read this before you install

- **#1 works best after a scan.** The README's order: scan at [isagentready.com](https://isagentready.com), install the skill, ask your agent to fix the failing checks, scan again. Skills install with `npx skills add <owner/repo>` ([vercel-labs/skills](https://github.com/vercel-labs/skills)).
- **#2 is a code package, not a skill.** Your developer (or your AI agent) adds it to the site. If your site does not run on one of those frameworks, the isagentready skills include server configs for nginx, Apache, Caddy and others.
- **#3 is not an llms.txt tool.** It is a Search Console server and command-line tool. If you want an llms.txt file, the same project has a free web generator: [seoskill.dev/tools/llms-txt-generator](https://seoskill.dev/tools/llms-txt-generator). After you sign in with Google, you can ask it things like "Can ChatGPT, Claude and Perplexity read my site?".
- These are small, independent projects. Read what a tool does before you let an agent change your site.

## Also worth knowing

- **[mlava/agent-ready-skills](https://github.com/mlava/agent-ready-skills)** (MIT): skills that run scans on [agent-ready.dev](https://agent-ready.dev), a checker with about 72 tests. It is not in the top 3 because its README says the skills need an `AGENT_READY_API_KEY`, and API access is on the **Pro plan ($19/month)**. The free plan (10 scans per 30 days, 25 pages per scan) is for scanning on the website itself. Pricing can change, so check the site.
- **webmcp-tools**: [GoogleChromeLabs/webmcp-tools](https://github.com/GoogleChromeLabs/webmcp-tools), tools for WebMCP (a way for a web page to offer actions to AI agents). Google says it is not an officially supported product.

## Quick start

1. Scan your site at [isagentready.com](https://isagentready.com), or run the free audit above.
2. Install tool #1 and ask your agent to fix the failing checks.
3. Add tool #2 so people get the design and AI agents get the clean version.
4. Scan again. Connect tool #3 to see your real Google numbers over the next weeks.

---

Idea from a reel by Sukhad Anand (techie007.dev). This page is a link list. It is not affiliated with any project above.
