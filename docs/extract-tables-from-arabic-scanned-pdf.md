# How to extract tables from a scanned Arabic PDF to JSON or CSV

Most PDF table tools (Tabula, Camelot, pdfplumber) read the PDF's text layer. A scanned PDF has none, and Arabic adds right-to-left order, joined letters and Eastern Arabic digits (٠١٢٣٤٥٦٧٨٩). The result is usually empty tables or reversed, broken text.

## What works
1. OCR each page with an Arabic-aware model.
2. Detect the table grid, then rebuild rows right to left.
3. Normalise Eastern Arabic digits to Western digits so numbers sort and sum.
4. Return one JSON object per row, with the column headers as keys.

## Doing it in one call
The [PDF Table Extractor (Arabic OCR)](https://apify.com/fifty50labs/pdf-table-extractor-arabic-ocr) actor does those four steps. Give it a PDF URL; get rows back as JSON, CSV or Excel. $15 per 1,000 pages, no subscription.

From an AI agent (Claude, Cursor, any MCP client), add the remote MCP server:

```
https://mcp.apify.com?tools=fifty50labs/pdf-table-extractor-arabic-ocr
```

with header `Authorization: Bearer <your Apify token>`, then ask: "Extract the tables from <PDF URL> as JSON."

## Good fits
- Saudi, Kuwaiti and UAE government circulars and tenders
- Scanned invoices, price lists and bank statements in Arabic
- Mixed Arabic/English tables

## Limits
Low-resolution or skewed scans lower accuracy. On our scanned Arabic test set, 23 of 27 rows came back fully correct.
