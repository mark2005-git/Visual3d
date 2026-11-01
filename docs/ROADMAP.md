# Roadmap

This roadmap is intentionally incremental. A milestone is complete only when its acceptance criteria can be demonstrated and verified.

## Foundation — repository and product contracts

- [x] Create private repository
- [x] Document product principles and initial architecture
- [x] Define the first scene and command contract
- [ ] Agree on license and contribution model
- [ ] Add initial issue labels and project tracking

## Alpha 0.1 — editable 3D workspace

- [ ] Set up the web application and repeatable development environment
- [ ] Render an interactive 3D viewport
- [ ] Create box, sphere, and cylinder primitives
- [ ] Select objects and show an object hierarchy
- [ ] Move, rotate, and scale selected objects
- [ ] Edit object properties in an inspector
- [ ] Implement deterministic structured scene commands
- [ ] Add undo and redo
- [ ] Export and import scene JSON
- [ ] Add automated tests for scene operations and serialization

**Acceptance demo:** build and edit a multi-part exploration vehicle using primitive objects, save the scene as JSON, reload it, and continue editing it.

## Alpha 0.2 — AI-assisted editing

- [ ] Define the AI command interface and provider adapter
- [ ] Convert natural-language instructions into proposed structured commands
- [ ] Preview and validate changes before applying them
- [ ] Explain rejected or ambiguous instructions
- [ ] Preserve undo/redo for AI-generated changes

## Beta — projects and richer assets

- [ ] Add project persistence and versioning
- [ ] Support more geometry and material workflows
- [ ] Add asset import/export where licensing and formats permit
- [ ] Improve scene organization and reusable components
- [ ] Add optional voice input

## Longer-term research

- Parametric and CAD-oriented geometry
- Mesh processing and Blender integration
- Engineering constraints and simulation
- Collaboration and sharing
- Desktop and mobile experiences

These longer-term items are research directions, not promised release dates or current capabilities.
