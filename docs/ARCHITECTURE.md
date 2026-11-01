# Architecture

## Goal

Visual3d turns user intent into structured, editable 3D scenes. The architecture separates intent interpretation, scene operations, scene data, and rendering so each layer can be tested independently.

## High-level flow

1. The user enters a text or voice instruction.
2. An intent layer interprets it and proposes one or more structured commands.
3. A validator checks command shape, object references, and supported operations.
4. The scene engine applies accepted operations to the scene model.
5. The viewport renders the updated scene.
6. The editor records the change so it can be undone or redone.

AI must not directly mutate renderer internals. It should propose structured operations that pass through the same validation and execution path as ordinary editor actions.

## Initial application boundaries

### Web client

Planned responsibilities:

- Editor layout, toolbar, viewport, hierarchy, and inspector
- Selection and direct manipulation
- Local editor state, history, and project interaction
- Scene serialization and import/export

Initial direction: React, TypeScript, Vite, Three.js, React Three Fiber, and Zustand.

### Scene model and engine

Planned responsibilities:

- Canonical scene representation
- Object creation, deletion, duplication, and transformation
- Material assignment and grouping
- Validation and serialization
- Undo/redo-compatible operations

Keep the scene model independent of Three.js objects where practical. Renderer objects are a presentation of scene data, not the canonical project format.

### API and AI orchestration

A FastAPI service may be introduced after the browser editor and deterministic command pipeline are working. It will eventually handle projects, authenticated sessions, AI-provider integration, and longer-running generation jobs.

Provider-specific code must sit behind an adapter so the application is not coupled to one model vendor.

## Trust and validation boundary

Treat model output as untrusted input. Validate every proposed command against a strict schema and current scene state. Reject unknown operation types, invalid values, and references to missing objects. Keep destructive operations explicit and make changes undoable.

## Future extensions

CAD kernels, mesh processing, simulation, collaboration, asset storage, and voice services are future capabilities. They are not prerequisites for Alpha 0.1 and should be introduced only with a concrete use case and test plan.
