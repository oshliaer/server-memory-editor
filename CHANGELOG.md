# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [0.1.0] — 2026-03-28

### Added
- HTML/CSS framework with light theme and full-screen SVG layout
- Control panels: search, details view, legend, statistics
- DataModel for JSONL/JSON parsing with exact-string deduplication
- Merge logic for duplicate entities (Set-based)
- Relation deduplication and ghost-node generation for dangling references
- D3 v7 force-directed graph visualization
- Dynamic Tableau10 color palette for entity types
- Shortened arrows (dynamic refX) with direction indicators
- Ghost nodes (dashed stroke) for dangling references
- Duplicate indicators (thick stroke) with count badges
- Interactive detail panel with clickable relations for graph navigation
- Neighbor highlighting and dimming on node selection
- Full-text search with type filtering
- Keyboard navigation (Escape to deselect)
- Graph statistics (entity/relation/type counts)
- JSONL export functionality
- Fit-to-view on simulation end
- Document-level drag-and-drop file loading
- Bug fix: fitToView called once instead of after every drag
- Bug fix: Improved relation items layout (two-line format: entity + relation type)

### Fixed
- Crash from dangling relations (now handled with ghost-nodes)
- Duplicate nodes appearing multiple times (now merged with count tracking)
- Arrow positioning with hardcoded refX (now dynamically calculated)
