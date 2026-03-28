# Memory JSONL Visualizer & Editor

Web-based visualizer and editor for MCP server-memory JSONL files. Interactive graph visualization with D3.js v7, full-text search, entity/relation management, and export capabilities.

Reverse-engineered from [mcp-memory-visualizer](https://github.com/dzivkovi/mcp-memory-visualizer) with bug fixes and enhancements.

## Version

Version: **0.1.0** ([changelog](CHANGELOG.md))

## Features

- **Graph Visualization**: D3.js force-directed layout with dynamic entity type coloring
- **Interactive Navigation**: Click entities to view details, hover to highlight neighbors
- **Search & Filter**: Full-text search with type filtering
- **Duplicate Detection**: Identifies and merges duplicate entities, shows count badges
- **Dangling References**: Handles unresolved relations with ghost-nodes
- **Data Export**: Export current graph state as JSONL
- **Statistics**: Entity, relation, and type counts
- **Keyboard Support**: Escape to deselect nodes

## Quick Start

1. Open `index.html` in a modern web browser
2. Load a JSONL file via drag-and-drop or file input
3. Click nodes to view entity details and connected relations
4. Use search box to filter by name or type
5. Export modified graph as JSONL

## File Format

The visualizer accepts standard MCP server-memory JSONL files:

```jsonl
{"type": "entity", "name": "Node Name", "entityType": "category"}
{"type": "relation", "from": "Node Name", "to": "Target Name", "relationType": "connects_to"}
{"type": "observation", "entityName": "Node Name", "contents": ["fact 1", "fact 2"]}
```

## Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- JavaScript enabled
- D3.js v7 (loaded from CDN)

## Architecture

- **DataModel**: Parses and manages JSONL data, handles deduplication and merging
- **Renderer**: D3.js-based SVG graph visualization with force simulation
- **UI**: Search, detail panel, legend, statistics, drag-and-drop file loading

## Agents & Automation

- Memory MCP Client: Integrates with MCP server-memory for real-time graph updates
- GitHub Issues: [Issue #7](https://github.com/oshliaer/server-memory-editor/issues/7) (umbrella), #1-#6 (phase 1), #8-#9 (interactive filtering)

## Configuration

- **Color Scheme**: Tableau10 dynamic palette for entity types
- **Force Simulation**: D3 force parameters (charge, link distance) are auto-tuned
- **Graph Bounds**: Fit-to-view automatically after simulation stabilization

## License

MIT
