# PDF Tables (Arabic OCR), Domain Availability, Core Web Vitals — MCP server

Three paid tools for AI agents, served as a remote MCP server through Apify. You pay per result; no subscription.

**Endpoint (streamable HTTP):**
```
https://mcp.apify.com?tools=fifty50labs/pdf-table-extractor-arabic-ocr,fifty50labs/domain-availability-checker-rdap,fifty50labs/core-web-vitals-crux-median-check
```
Auth: `Authorization: Bearer <your Apify API token>`.

Registry name: `io.github.mdfifty50-boop/pdf-tables-domains-web-vitals`

## Tools

| Tool | Use for | Not for | Price |
|---|---|---|---|
| [pdf-table-extractor-arabic-ocr](https://apify.com/fifty50labs/pdf-table-extractor-arabic-ocr) | Tables from scanned or Arabic/RTL PDFs to JSON rows | Free-text summaries | $15 / 1,000 pages |
| [domain-availability-checker-rdap](https://apify.com/fifty50labs/domain-availability-checker-rdap) | Bulk domain availability via RDAP | Premium/aftermarket pricing | $15 / 1,000 domains |
| [core-web-vitals-crux-median-check](https://apify.com/fifty50labs/core-web-vitals-crux-median-check) | Pass/fail CWV verdict: real-user CrUX data plus median of 3 lab runs | Full Lighthouse reports | $25 / 1,000 audits |

## Client config

```json
{
  "mcpServers": {
    "fifty50labs": {
      "url": "https://mcp.apify.com?tools=fifty50labs/pdf-table-extractor-arabic-ocr,fifty50labs/domain-availability-checker-rdap,fifty50labs/core-web-vitals-crux-median-check",
      "headers": { "Authorization": "Bearer YOUR_APIFY_TOKEN" }
    }
  }
}
```

## Guides
- [Extract tables from a scanned Arabic PDF](docs/extract-tables-from-arabic-scanned-pdf.md)

## Limits
- Short reserved or premium names can read as available in RDAP; results carry a warning.
- OCR accuracy depends on scan quality.
