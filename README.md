# OutSlide MCP

[![AllMCPs Verified](https://allmcps.com/api/badge/outslide-mcp?style=shield)](https://allmcps.com/mcp/outslide-mcp)

OutSlide exposes a public, rate-limited MCP preview for planning slide decks from
a topic or inline CSV/JSON. The preview returns a structured 3–8 slide outline
and a `continue_url` for building the presentation in the OutSlide web workspace.

The public MCP endpoint currently exposes one tool:

- `outslide_preview_outline` — free, no API key or wallet required.

It does **not** claim to generate PPTX or PDF files through MCP yet.

## Connect

Codex CLI:

```sh
codex mcp add outslide --url https://outslide.ai/api/x402/mcp
```

Any Streamable HTTP MCP client:

```json
{
  "mcpServers": {
    "outslide": {
      "type": "streamable-http",
      "url": "https://outslide.ai/api/x402/mcp"
    }
  }
}
```

## Try it

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
