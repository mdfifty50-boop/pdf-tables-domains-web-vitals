# PDF Tables (Arabic OCR), Domain Availability, Core Web Vitals, OpenAI Shutdown Scanner — MCP server

Four tools for AI agents, served as a remote MCP server through Apify: three pay per result, one free. No subscription.

**Endpoint (streamable HTTP):**
```
https://mcp.apify.com?tools=fifty50labs/pdf-table-extractor-arabic-ocr,fifty50labs/domain-availability-checker-rdap,fifty50labs/core-web-vitals-crux-median-check,fifty50labs/openai-deprecation-scanner
```
Auth: `Authorization: Bearer <your Apify API token>`.

Registry name: `io.github.mdfifty50-boop/pdf-tables-domains-web-vitals`

## Tools

| Tool | Use for | Not for | Price |
|---|---|---|---|
| [pdf-table-extractor-arabic-ocr](https://apify.com/fifty50labs/pdf-table-extractor-arabic-ocr) | Tables from scanned or Arabic/RTL PDFs to JSON rows | Free-text summaries | $15 / 1,000 pages |
| [domain-availability-checker-rdap](https://apify.com/fifty50labs/domain-availability-checker-rdap) | Bulk domain availability via RDAP | Premium/aftermarket pricing | $15 / 1,000 domains |
| [core-web-vitals-crux-median-check](https://apify.com/fifty50labs/core-web-vitals-crux-median-check) | Pass/fail CWV verdict: real-user CrUX data plus median of 3 lab runs | Full Lighthouse reports | $25 / 1,000 audits |
| [openai-deprecation-scanner](https://apify.com/fifty50labs/openai-deprecation-scanner) | Find OpenAI models/endpoints being shut down (gpt-4o, o3, gpt-5, tts-1, whisper-1, Assistants, Agent Builder, /v1/prompts) in n8n/Make JSON, code or a public GitHub repo, with location, shutdown date, days left and replacement | Editing the code; non-OpenAI models; private repos | Free |

## Client config

```json
{
  "mcpServers": {
    "fifty50labs": {
      "url": "https://mcp.apify.com?tools=fifty50labs/pdf-table-extractor-arabic-ocr,fifty50labs/domain-availability-checker-rdap,fifty50labs/core-web-vitals-crux-median-check,fifty50labs/openai-deprecation-scanner",
      "headers": { "Authorization": "Bearer YOUR_APIFY_TOKEN" }
    }
  }
}
```

## Guides
- [Extract tables from a scanned Arabic PDF](docs/extract-tables-from-arabic-scanned-pdf.md)

## Limits
- The OpenAI shutdown table is checked by hand against platform.openai.com/docs/deprecations (last 14 Nov 2026).
- Short reserved or premium names can read as available in RDAP; results carry a warning.
- OCR accuracy depends on scan quality.

Need an OpenAI model migration done before the deadline? Fixed-price migration with before/after proof: https://rudoodtujjar.gumroad.com/l/csdpjv
