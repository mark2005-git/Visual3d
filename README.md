# Visual3d

**From imagination to editable 3D.**

Visual3d is a web-first, AI-assisted 3D creation platform. Its goal is to let people describe an idea in natural language, build it as a real 3D scene, and refine the result through direct manipulation and structured commands.

The project will grow incrementally from a reliable, editable 3D workspace into a platform for more advanced design and engineering workflows.

## Product principles

- **Editable output:** generated results must be real scene objects, not just images.
- **Human-directed creation:** users can describe, select, inspect, and manipulate individual components.
- **Structured execution:** AI suggestions are translated into validated scene operations before they change a project.
- **Progressive capability:** begin with dependable 3D primitives; add richer geometry, collaboration, CAD, and simulation when the foundations are ready.
- **Portable projects:** scenes should have a documented, versionable representation and support import/export.

## Initial milestone: Alpha 0.1

The first milestone focuses on a dependable browser-based 3D editor:

- Interactive 3D viewport
- Create box, sphere, and cylinder primitives
- Select, move, rotate, and scale objects
- Object hierarchy and property inspector
- Deterministic structured commands for creating and modifying objects
- Undo and redo
- Scene JSON export and import

The first demo target is an editable exploration vehicle assembled from primitive geometry. This is a workflow demonstration, not a claim of photorealistic or engineering-ready output.

## Planned architecture

| Area | Initial direction |
|---|---|
| Web app | React, TypeScript, Vite |
| 3D viewport | Three.js and React Three Fiber |
| State | Zustand |
| API | Python and FastAPI (introduced when needed) |
| Scene contracts | Shared, validated TypeScript/Pydantic-compatible schema |
| AI integration | Provider-independent orchestration, added after deterministic commands work |

Technology choices may evolve as prototypes and verification reveal better options.

## Repository layout

```text
apps/
  web/                 Browser editor (planned)
  api/                 Backend API (planned)
packages/
  scene-schema/        Shared scene and command contracts (planned)
  design-system/       Reusable UI components (planned)
engines/
  scene-engine/        Geometry and scene operations (planned)
docs/
  ARCHITECTURE.md
  DEVELOPMENT.md
  ROADMAP.md
  SCENE_SCHEMA.md
```

## Project status

This repository currently contains the project foundation and design documents. Implementation will be added in small, verifiable milestones. See [the roadmap](docs/ROADMAP.md) for scope and [development notes](docs/DEVELOPMENT.md) for setup.

## Contributing

Read [CONTRIBUTING.md](CONTRIBUTING.md) before opening an issue or pull request. Early contributions should keep the Alpha 0.1 scope small and testable.

## License

No license has been selected yet. Until one is added, all rights are reserved by default; do not assume this repository is open source or that its contents may be reused.
