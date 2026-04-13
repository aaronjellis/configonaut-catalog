# Configonaut Catalog

MCP server catalog for [Configonaut](https://github.com/aaronjellis/Configonaut). The app fetches `catalog.json` on startup to discover available MCP servers for the marketplace.

## Structure

`catalog.json` contains server entries with:
- **id** — unique identifier
- **name / description** — display metadata
- **category** — grouping (development, database, cloud, etc.)
- **transport** — `"stdio"` or `"remote"`
- **requirements** — runtime prerequisites (`["node"]`, `["python", "uv"]`, etc.)
- **config** — default MCP server configuration block
- **requiredSecrets** — env vars the user must fill in

## Contributing

See the main Configonaut repo for contribution guidelines.
