# Ordo plugin for Grok Build

Connects [Grok Build](https://x.ai/build) to the hosted [Ordo](https://ordoscheduler.com) MCP server.

- **Endpoint:** `https://ordoscheduler.com/mcp`
- **Auth:** `Authorization: Bearer ${ORDO_TOKEN}`
- **Token:** Ordo user API token from the Ordo UI. Not stored in this repo.
- **License:** MIT

This repo is the Grok Build plugin wrapper. The scheduler itself lives at https://github.com/nathanielgraham/ordo.

## Setup

```bash
export ORDO_TOKEN=your_token_here

# After listing in xai-org/plugin-marketplace:
grok plugin install ordo --trust

# Until then:
grok mcp add --transport http ordo https://ordoscheduler.com/mcp \
  --header "Authorization: Bearer ${ORDO_TOKEN}"
grok mcp doctor ordo
```

## Security

No shell, hooks, or postinstall. Grok Build only calls `https://ordoscheduler.com/mcp` with `ORDO_TOKEN` from the environment.
