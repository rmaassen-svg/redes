# AGENTS.md

This repository is a small static web app for visualizing country trade or production networks. The implementation is centered in [Index.html](Index.html), with HTML, CSS, and JavaScript all in a single file.

## What matters most

- Keep changes compatible with the existing D3-based rendering flow.
- Prefer small, targeted edits inside [Index.html](Index.html) rather than introducing new frameworks or build tooling.
- Preserve the app's CSV workflow: nodes and links are loaded from files and parsed dynamically.
- Maintain the Spanish UI copy unless a task explicitly requires otherwise.

## Project structure

- [Index.html](Index.html): complete application source, including layout, styles, data parsing, state management, and rendering logic.

## Coding conventions

- Treat the app as a single-file front-end project. Do not add a framework unless the user explicitly asks for one.
- Preserve the existing `state` object and the `CONF` configuration block when extending features.
- Update rendering logic in the same area as related visual features; the file is organized by sections.
- Keep selectors and DOM IDs consistent with the current UI elements to avoid breaking tab switching, legends, overlays, or file loaders.
- If you add new controls, prefer styling that matches the current design system already defined in the CSS section.

## Data and behavior expectations

- CSV input is expected for both nodes and links.
- Delimiter detection is already implemented and should remain robust for comma and semicolon separated files.
- The app supports multiple visualization modes (cuerdas, concéntrico, edge bundling), so new features should not break the mode switcher or shared rendering pipeline.
- Keep the network interactions (hover, tooltip, isolation, filtering, and selected-node highlighting) working when you change visual logic.

## Validation

- There is no automated test suite in this repo at the moment.
- Validate UI changes by opening the project in a browser and checking that:
  1. the app loads without JavaScript errors,
  2. CSV files can be imported,
  3. network layers render correctly,
  4. tab switching and filtering still behave as expected.

## Recommended workflow for AI agents

- Start by locating the relevant rendering or state-management section in [Index.html](Index.html).
- Make the smallest possible change that addresses the task.
- Confirm the visual behavior manually in-browser rather than introducing new tooling or test scaffolding.

## Useful next customization

If the project grows, a good follow-up would be a dedicated browser-preview or front-end workflow skill for static HTML/D3 debugging, but only after the repo has more structure or tooling.
