# Regex Formatter API

Format, minify, and explain regex patterns via HTTP API.

## Endpoints

### POST /format
Validate and return a formatted regex pattern.
```bash
curl -X POST https://regex-formatter.vercel.app/format \
  -H "Content-Type: application/json" \
  -H "X-API-Key: demo-key-change-me" \
  -d '{"pattern": "[a-z]+\\d{2,4}"}'
```

### POST /minify
Remove unnecessary whitespace from regex patterns.
```bash
curl -X POST https://regex-formatter.vercel.app/minify \
  -H "Content-Type: application/json" \
  -H "X-API-Key: demo-key-change-me" \
  -d '{"pattern": "[a-z]+ \\d{2, 4}"}'
```

### POST /explain
Get explanation of regex components.
```bash
curl -X POST https://regex-formatter.vercel.app/explain \
  -H "Content-Type: application/json" \
  -H "X-API-Key: demo-key-change-me" \
  -d '{"pattern": "^[\\w]+@([a-z]+\\.)+[a-z]{2,}$"}'
```

### POST /test
Test regex against sample strings.
```bash
curl -X POST https://regex-formatter.vercel.app/test \
  -H "Content-Type: application/json" \
  -H "X-API-Key: demo-key-change-me" \
  -d '{"pattern": "\\\\d{3}-\\\\d{3}"}'
```

### GET /health
Health check endpoint (no auth required).

## Response Format
```json
{
  "pattern": "...",
  "valid": true,
  "minified": "...",
  "components": [...],
  "flags": {...}
}
```

## Pricing (Suggested)
- $19/month: 1000 requests/day
- $49/month: 10000 requests/day
- List on RapidAPI for discoverability

## Postman
[![Run in Postman](https://run.pstmn.io/button.svg)](https://raw.githubusercontent.com/BT-Builds/regex-formatter/main/postman_collection.json)
