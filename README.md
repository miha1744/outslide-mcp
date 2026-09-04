# OutSlide Creative Workspace | MCP for Codex and Claude Code

[![AllMCPs Verified](https://allmcps.com/api/badge/outslide-mcp?style=shield)](https://allmcps.com/mcp/outslide-mcp)

OutSlide is an AI creative workspace for images, video, music, audio and presentations.
This repository documents account-linked image creation and the separate public
outline connector for Codex and Claude Code.

Create and reuse assets in one workspace. Choose an available model and review the
credit cost before generation.

## Create images through your account

Connect your OutSlide account, choose an available image model, and review the
credit quote before generation. Set a spending limit for the connection and
revoke access when needed. Generated images are saved in your OutSlide workspace
for download and reuse.

[Set up image creation](https://outslide.ai/mcp?utm_source=github&utm_medium=referral&utm_campaign=mcp_image_launch&utm_content=readme&test_id=mcp_image_01)

The account-linked endpoint is `https://outslide.ai/api/mcp`. Follow the Settings
instructions linked above to grant image access with a credit cap and expiry.
It is separate from the anonymous outline endpoint documented below.

The account-linked image workflow has been verified in production through HTTP
MCP. Codex CLI model discovery and quotes have been checked; Claude Code has not
yet been independently tested. This does not claim that every creative format
has an end-to-end verified MCP workflow.

## Public outline preview

**Available through this public MCP connector today:** preview a 3–8 slide outline
from a topic or inline CSV/JSON, then continue the presentation in OutSlide. Image,
video and audio creation happen in the signed-in web workspace, not through this
MCP endpoint. The preview returns structured slide titles and briefs plus a
`continue_url` for the next step.

The public MCP endpoint currently exposes one tool:

- `outslide_preview_outline` — free, no API key or wallet required.

It does **not** claim to generate PPTX or PDF files through MCP yet.

## Connect to the public outline preview

### Codex

```sh
codex mcp add outslide --url https://outslide.ai/api/x402/mcp
```

### Claude Code

```sh
claude mcp add --transport http outslide https://outslide.ai/api/x402/mcp
```

These are CLI commands, not Claude Desktop configuration. Other clients must
support remote Streamable HTTP and use their own connector setup instructions.

## Try the public outline preview

Ask your MCP client:

> Use OutSlide to outline a six-slide thesis defense about how remote work
> affects onboarding. Include the research question, method, findings,
> limitations, and contribution.

Prefer the browser? [Preview a personalized thesis-defense outline](https://outslide.ai/templates/thesis-defense/?utm_source=github&utm_medium=mcp_repository&utm_campaign=mcp_preview_launch&utm_content=thesis-readme&cohort=thesis_research&test_id=mcp_readme_thesis) with no account or card, then continue it in OutSlide.

You can also pass inline CSV or JSON with `data`, set `data_format`, choose
`n_slides` from 3 to 8, and select a supported `language`.

Do not submit confidential or personal data to the public preview.

## Links

- [OutSlide MCP setup](https://outslide.ai/mcp?utm_source=github&utm_medium=mcp_repository&utm_campaign=mcp_preview_launch&utm_content=readme_setup&cohort=agent&test_id=mcp_repo_setup)
- [Public discovery manifest](https://outslide.ai/.well-known/mcp.json)
- [Official MCP Registry entry](https://registry.modelcontextprotocol.io/v0.1/servers?search=io.github.miha1744%2Foutslide)
- [Smithery listing](https://smithery.ai/servers/kapper3228/outslide)

This repository contains public discovery metadata and setup instructions only.
The hosted OutSlide service remains proprietary.
