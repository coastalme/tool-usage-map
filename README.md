# tool-usage-map

A Leaflet dashboard showing where the software tools in this repository have been used around the world.

## Features

- Interactive world map with marker clustering
- Dark-themed Leaflet map (CartoDB Dark Matter tiles)
- Sidebar with filterable results list
- Filter by tool name, year, or free-text search (location / organisation)
- Header statistics: total uses, countries, and distinct tools
- Click a sidebar item or map marker to highlight and zoom to that location

## Usage

Because the dashboard loads `data/tools.json` via `fetch`, it must be served from an HTTP server rather than opened as a plain file.

```bash
# Python 3
python3 -m http.server 8080
# then open http://localhost:8080
```

## Data

Tool usage records are stored in [`data/tools.json`](data/tools.json).
Each entry has the following fields:

| Field | Description |
|-------|-------------|
| `id` | Unique integer identifier |
| `tool` | Tool name |
| `version` | Tool version used |
| `location` | Human-readable location string |
| `lat` / `lng` | Geographic coordinates |
| `organisation` | Organisation that used the tool |
| `year` | Year of use |
| `description` | Brief description of the use case |

To add a new usage record, append an object to `data/tools.json` following the schema above.

