# Free100leads.com ChatGPT plugin

Read-only ChatGPT app. Ask whether a market is covered and what a record contains. It returns coverage only, never contacts.

This repo is the plugin archive source (`plugin.json`, `mcp.json` and the two images) used to submit Free100leads.com to ChatGPT. The server itself is hosted by Free100leads.com and needs no account and no API key.

## What is a ChatGPT plugin?

A ChatGPT plugin (also called an app) lets ChatGPT call an outside service while it answers you. Here ChatGPT calls the Free100leads.com MCP server, a read-only endpoint, and shows you the result with a link back to the full page on the site.

## About Free100leads.com

Free100leads.com is a B2B contact database searchable by country, industry, company size and job title, with a free daily allowance. Visit it at https://free100leads.com.

## Endpoint

```
https://free100leads.com/api/mcp
```

Model Context Protocol over Streamable HTTP, read-only, no authentication.

## Files

- `plugin.json`: name, description, prompts, links to the privacy policy and terms.
- `mcp.json`: points ChatGPT at the endpoint above.
- `assets/icon.png`, `assets/logo.png`: icons.

## Build the archive

Put the files at the ZIP root, not inside a folder:

```
python -c "import zipfile;z=zipfile.ZipFile('free100leads-plugin.zip','w',zipfile.ZIP_DEFLATED);[z.write(f,f) for f in ['plugin.json','mcp.json','assets/icon.png','assets/logo.png']];z.close()"
```

Bump `version` in `plugin.json` for any metadata change. Server-side changes need no new archive.

## More from Free100leads.com

- Website: https://free100leads.com
- Developer docs for Claude: https://free100leads.com/docs/claude
- Developer docs for ChatGPT: https://free100leads.com/docs/api
- Browser extension: https://github.com/ExpatsListORG/free100leads-browser-extension
- Claude connector: https://github.com/ExpatsListORG/free100leads-claude-connector
- Privacy policy: https://free100leads.com/privacy
- Terms of service: https://free100leads.com/terms
- Contact: https://free100leads.com/contact

## License

MIT. See `LICENSE`.
