# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [0.1.1] — 2026-03-28

### Fixed
- fitToView now called only once on initial load instead of after every drag (added `fitted` flag)

### Changed
- Duplicate and relation item layout: two-line format displays entity name (line 1, clickable) and relationType (line 2, smaller font) to prevent text truncation on long relation types
- DataModel now preserves original versions of duplicates in `_versions` array (entityType and observations)

### Added
- Clickable duplicate version viewer: "Found N times — show versions" in detail panel reveals all original records with their entityType and observations
- Clickable filters in statistics panel: clicking "N dup" or "N ghost" filters graph to show only duplicates or ghost nodes; clicking again resets filter
- Test data updated: memory.jsonl expanded with duplicate entities having different entityType/observations and additional ghost node relationships

## [0.1.0] — 2026-03-28

### Added
- HTML/CSS framework with light theme and full-screen SVG layout
- Control panels: search, details view, legend, statistics
- DataModel for JSONL/JSON parsing with exact-string deduplication
- Merge logic for duplicate entities (Set-based)
- Relation deduplication and ghost-node generation for dangling references
- D3 v7 force-directed graph visualization
- Dynamic Tableau10 color palette for entity types
- Arrows shortened to node boundaries in ticked() with fixed small marker refX
- Ghost nodes (dashed stroke) for dangling references
- Duplicate indicators (thick stroke) with info in detail panel
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
- Arrow positioning with hardcoded refX=25 (now lines shortened to node boundary in ticked(), marker uses fixed small refX)
