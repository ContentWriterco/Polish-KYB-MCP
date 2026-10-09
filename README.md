# Polish KYB MCP Server

Verify Polish business partners in one place: registry profile, management and shareholders, beneficial owners, insolvency and restructuring, court gazette notices, sanctions lists and financial supervision licences.

Remote MCP server (Streamable HTTP), read-only, hosted by [Compabase](https://compabase.com/due-diligence).

```
https://compabase.com/api/mcp/kyb
```

## Tools

| Tool | What it does |
|---|---|
| `search_companies / get_company` | Find the company and read its KRS registry profile and VAT status. |
| `get_company_people / get_company_beneficiaries` | Management board, supervisory board, shareholders and beneficial owners (CRBR). |
| `get_company_debt_registry` | Insolvency and restructuring proceedings (KRZ). |
| `get_company_court_gazette` | Court and Commercial Gazette (MSiG) notices. |
| `get_company_sanctions / get_company_financial_supervision` | Sanctions lists and KNF financial supervision register. |
| `get_company_secured_liabilities / get_company_articles` | Secured liabilities and articles of association. |

## Example prompts

- Run a KYB check on the company with NIP 5260250995.
- Who are the beneficial owners of KRS 0000028860?
- Is this company in insolvency proceedings or on a sanctions list?

## Authentication

Sign in with your Compabase account (OAuth) in clients that support it, or send an MCP key: create one at https://compabase.com/integrations?tab=mcp and pass it as `Authorization: Bearer mcpk_…` or append `?apiKey=mcpk_…` to the URL. Queries count toward your Compabase plan.

## Setup

**Claude (claude.ai, Desktop):** Settings → Connectors → Add custom connector → paste the URL above (add `?apiKey=mcpk_…` if you use a key).

**Cursor / VS Code / Windsurf** (`mcp.json`):

```json
{
  "mcpServers": {
    "polish-kyb": {
      "url": "https://compabase.com/api/mcp/kyb",
      "headers": { "Authorization": "Bearer mcpk_YOUR_KEY" }
    }
  }
}
```

**ChatGPT:** Settings → Apps → Developer mode → Create → paste the URL.

## About

Part of the [Compabase](https://compabase.com/docs/mcp/) MCP family. Full Compabase MCP (all Polish company data tools): https://compabase.com/api/mcp.

Questions: contact@compabase.com

## Gemini CLI

```bash
gemini extensions install https://github.com/ContentWriterco/Polish-KYB-MCP
```

Gemini CLI asks for your Compabase MCP key during installation (create one at https://compabase.com/integrations?tab=mcp).

## Setup guides

Step-by-step setup guides for Claude, ChatGPT, Gemini, Grok, Le Chat, Perplexity, Cursor, VS Code and Claude Code: https://compabase.com/docs/mcp/connect/
