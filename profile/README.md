<h1 align="center">Seolyticize</h1>

<p align="center"><b>SEO for agencies and the agents that run sites.</b><br>
Search Console and GA4, a 129-check site crawler, cookieless analytics, IndexNow, AI-assistant visibility, rank tracking and keyword research — ~200 tools over one API, MCP, SDKs and a CLI.</p>

<p align="center">
  <a href="https://seolyticize.com">Website</a> ·
  <a href="https://seolyticize.com/AGENTS.md">Agent quick start</a> ·
  <a href="https://seolyticize.com/docs">Docs</a> ·
  <a href="https://seolyticize.com/docs/c/api-reference">API reference</a> ·
  <a href="https://seolyticize.com/status">Status</a>
</p>

---

### A site in four calls

```text
POST /api/v1/claim           →  an invite code becomes a key for just that site
onboard_site                 →  one deploy manifest: files, tags, analytics snippet
(deploy)
verify_site                  →  ✓ IndexNow  ✓ Google ownership + Search Console  ✓ analytics  ✓ first crawl
get_next_steps               →  the weekly loop, with every call filled in
```

No one opens Google's settings: the agency's Google account proves ownership with a file you deploy.

### Talk to the API

|                 | Install                                                                       |                                                                 |
| --------------- | ----------------------------------------------------------------------------- | --------------------------------------------------------------- |
| **TypeScript**  | `npm i @seolyticize/sdk`                                     | [sdk-typescript](https://github.com/Seolyticize/sdk-typescript) |
| **Python**      | `pip install git+https://github.com/Seolyticize/sdk-python`                   | [sdk-python](https://github.com/Seolyticize/sdk-python)         |
| **Go**          | `go get github.com/Seolyticize/sdk-go`                                        | [sdk-go](https://github.com/Seolyticize/sdk-go)                 |
| **CLI**         | `npm i -g @seolyticize/cli`                                             | [cli](https://github.com/Seolyticize/cli)                       |
| **MCP**         | `claude mcp add --transport http seolyticize https://seolyticize.com/api/mcp` | sign in, or a key header · stdio: `seolyticize mcp`             |
| **Claude Code** | `/plugin marketplace add Seolyticize/claude-plugin`                           | [claude-plugin](https://github.com/Seolyticize/claude-plugin)   |
| **REST**        | `POST https://seolyticize.com/api/v1/tools/{name}`                            | [OpenAPI](https://seolyticize.com/api/v1/openapi.json)          |

Every SDK is generated from the registry that runs the API, so they cannot drift from it. Errors carry a stable `code`, the `next` call, and a `requestId`.

### On your site

|                            |                                                                                                                          |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **Next.js / React**        | [`next`](https://github.com/Seolyticize/next) — `<Analytics />`, the IndexNow key route, `seolyticize-notify-deploy`     |
| **WordPress**              | [`wordpress`](https://github.com/Seolyticize/wordpress) — analytics, IndexNow key, publish pings, insights in the editor |
| **PHP** (Laravel, Symfony) | [`site-php`](https://github.com/Seolyticize/site-php)                                                                    |
| **Ruby** (Rails, Rack)     | [`site-ruby`](https://github.com/Seolyticize/site-ruby)                                                                  |
| **Python** (Django, Flask) | `seolyticize.site` in [`sdk-python`](https://github.com/Seolyticize/sdk-python)                                          |
| **Go**                     | package `site` in [`sdk-go`](https://github.com/Seolyticize/sdk-go)                                                      |
| **Anything**               | `<script defer data-site="KEY" src="https://seolyticize.com/a.js"></script>`                                             |

Analytics is cookieless, honours Do Not Track and Global Privacy Control, and never sends a query string but `utm_*` tags.

<sub>Security issues: report privately through the repository's **Security → Report a vulnerability**.</sub>
