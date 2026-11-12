# INSTRUCTIONS.md — Agent Reach (Rainer-Silva fork)

This file was added to the fork for Rainer Andrade Silva on 12 November 2026 (Europe/Stockholm). It is not part of the upstream project.

- **Upstream:** https://github.com/Panniantong/Agent-Reach
- **This fork:** https://github.com/Rainer-Silva/Agent-Reach
- **License:** MIT
- **Reviewed snapshot:** 111,184 stars, 9,962 forks, last upstream commit 8 Nov 2026, 03:17 CET (Europe/Stockholm), latest release v1.6.1. The Instagram reel claimed about 108k stars; the live count is in the same range.

## What it is

Agent Reach is a Python CLI that lets a coding agent search and *read* platforms it often cannot reach well: X (Twitter), Reddit, YouTube (metadata and transcripts), GitHub, Bilibili, XiaoHongShu, LinkedIn jobs, Facebook, Instagram, and others. Default channels (GitHub, YouTube, web, Bilibili, V2EX) work without login. Optional and “experimental” channels often copy a browser login into a dedicated background browser, or ask you to log in yourself.

It is read-only by design (no posting, liking, or messaging). The author warns that the PyPI package named `agent-reach` is **not** this project — never install it from PyPI.

## Can it cut token usage / cost?

| Question | Honest answer |
|---|---|
| Cut Grok Bot / this assistant’s usage? | **No.** |
| Cut LLM token count? | **No.** It usually *increases* tokens, because scraped posts, transcripts and pages are then sent into the model’s context. |
| Cut paid search / social API fees? | **Possibly**, by scraping or using unofficial tools instead of official APIs. That is a ToS risk, not a token-saving feature. |
| Fit for Rainer’s setup? | Only as a research tool for your own agents, and only for platforms whose terms you are willing to follow. It does not help Grok Bot bills. |

## Setup (do not run until you have decided to try it)

1. Do **not** install `agent-reach` from PyPI.
2. Read upstream `docs/install.md` and `docs/README_en.md` first.
3. Official install uses `uv` and the GitHub release zip:

```bash
uv tool install https://github.com/Panniantong/Agent-Reach/releases/latest/download/agent-reach.zip
agent-reach setup
```

4. To test the fork instead, install from this repository only after you have reviewed the current release artifacts. Prefer a tagged release over an unreviewed `main`.
5. Start with default, no-login channels (GitHub, YouTube, web). Do not enable Twitter, Reddit, LinkedIn, Instagram, Facebook, or other login channels until you have decided it is acceptable to copy or reuse a session — and prefer a throwaway account, never a main account.
6. If a tool needs a Groq or OpenAI key (YouTube speech-to-text, some podcasts), enter it in your own terminal with `agent-reach configure …`. Never paste keys into chat.

## Risks and caveats

- **Session copying is the main risk.** For login-required sites it can copy that site’s login from your Chrome profile into a dedicated browser. Upstream says it does not read the password store and does not change the original browser, but cookies/sessions are still sensitive. Use a secondary account if you enable those channels at all.
- **Terms of service.** Scraping X, Reddit, YouTube, LinkedIn, Instagram or Facebook, or automating a logged-in session, can violate those sites’ terms and can get the account restricted. “Zero API fees” is not the same as “allowed.”
- **Supply chain.** The README tells you to paste a raw GitHub install URL into an agent and let it run commands. Do not do that blindly. Also ignore any official-looking `agent-reach` package on PyPI.
- **Sponsored proxy / unlocker services** (Bright Data, RapidProxy, BrowserAct) may cost money and are used to bypass anti-bot defences. Do not sign up or spend without approval.
- **Star counts are unusually high** for a repo created on 24 February 2026 (about 428 stars/day). Treat popularity as marketing, not a security review.
- **No passwords, cookies, or API keys in chat.**

## Cost note

Running anything that needs paid APIs (Groq, OpenAI, proxy services, residential IPs) or paid servers requires Rainer’s spend approval first. Forking and reading the code is free. A local trial of the default no-login channels can be 0 kr if you already have Python/`uv` and do not add paid keys.

## Recommendation

Not a token-saving tool. Useful only if you later want a coding agent to read public GitHub / YouTube / web content. Leave login-based social scrapers off unless you have a clear need, a secondary account, and have accepted the ToS risk. Scan the skill with SkillSpector before installing it into an agent.
