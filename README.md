# Configonaut Catalog

MCP server catalog for [Configonaut](https://github.com/aaronjellis/Configonaut). The app fetches `catalog.json` on startup to discover available MCP servers for the marketplace.

## Structure

`catalog.json` contains server entries with:
- **id**: unique identifier
- **name / description**: display metadata
- **category**: grouping (development, database, cloud, etc.)
- **transport**: `"stdio"` or `"remote"`
- **requirements**: runtime prerequisites (`["node"]`, `["python", "uv"]`, etc.)
- **config**: default MCP server configuration block
- **envVars**: credential metadata users must fill in

Remote servers may use `config.url` directly. When a hosted endpoint needs a
custom secret header, an stdio bridge can read a supported `env` config field
and forward that header without storing the secret in the catalog.

## Validation

Before opening a catalog change:

```bash
python3 -m json.tool catalog.json >/dev/null
```

Validate against the canonical schema linked by `$schema`. Also check that
category ids are unique, every server id is unique, and each server category
exists in `categories`.

## Contributing

See the main Configonaut repo for contribution guidelines.
