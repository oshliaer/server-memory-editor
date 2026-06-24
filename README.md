# Memory JSONL Visualizer & Editor

Web-based visualizer for [MCP server-memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) JSONL files. Interactive graph visualization with D3.js v7, full-text search, and export capabilities. Editing features are planned for future phases.

Reverse-engineered from [mcp-memory-visualizer](https://github.com/dzivkovi/mcp-memory-visualizer) with bug fixes and enhancements.

## Version

Version: **0.2.0** ([changelog](CHANGELOG.md))

## Features

- **Graph Visualization**: D3.js force-directed layout with dynamic entity type coloring
- **Interactive Navigation**: Click entities to view details and highlight neighbors
- **Search**: Full-text search across name, entity type, and observations
- **Duplicate Detection**: Identifies and merges duplicate entities with version tracking
- **Dangling References**: Handles unresolved relations with ghost-nodes
- **Data Export**: Export current graph state as JSONL
- **Statistics**: Entity and relation counts with duplicate/ghost filters
- **Keyboard Support**: Escape to deselect nodes

## Quick Start

1. Open `index.html` in a modern web browser
2. Load a JSONL file via drag-and-drop or file input
3. Click nodes to view entity details and connected relations
4. Use search box to filter by name or type
5. Export modified graph as JSONL

## File Format

The visualizer accepts standard [MCP server-memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) JSONL files:

```jsonl
{"type": "entity", "name": "Node Name", "entityType": "category", "observations": ["fact 1", "fact 2"]}
{"type": "relation", "from": "Node Name", "to": "Target Name", "relationType": "connects_to"}
```

Also supports JSON format: `{"entities": [...], "relations": [...]}`

## Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- JavaScript enabled
- D3.js v7 (loaded from CDN)

## Architecture

- **DataModel**: Parses and manages JSONL data, handles deduplication and merging
- **Renderer**: D3.js-based SVG graph visualization with force simulation
- **UI**: Search, detail panel, legend, statistics, drag-and-drop file loading

## Agents & Automation

- MCP integration planned for phase 3
- GitHub Issues: [Issue #7](https://github.com/oshliaer/server-memory-editor/issues/7) (umbrella), #1-#6 (phase 1), #8-#9 (interactive filtering)

## Configuration

- **Color Scheme**: Tableau10 dynamic palette for entity types
- **Force Simulation**: D3 force parameters (charge, link distance) are auto-tuned
- **Graph Bounds**: Fit-to-view automatically after simulation stabilization

## License

MIT
