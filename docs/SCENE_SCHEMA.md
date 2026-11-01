# Scene Schema — initial contract

This document describes the first version of the Visual3d scene model. It is a design contract, not yet an implemented or versioned API. The implementation must add explicit schema validation and migration rules before persisted projects depend on it.

## Design requirements

- Every scene and object has a stable unique identifier.
- Object transforms use explicit position, rotation, and scale values.
- Geometry and material data are serializable.
- Relationships refer to object IDs, not renderer instances.
- Unknown or invalid operations are rejected.
- Schema changes must be versioned.

## Conceptual scene shape

```json
{
  "schemaVersion": 1,
  "sceneId": "scene-id",
  "name": "Untitled scene",
  "objects": [
    {
      "id": "object-id",
      "name": "Box",
      "type": "mesh",
      "geometry": {
        "kind": "box",
        "parameters": {
          "width": 1,
          "height": 1,
          "depth": 1
        }
      },
      "transform": {
        "position": [0, 0, 0],
        "rotation": [0, 0, 0],
        "scale": [1, 1, 1]
      },
      "material": {
        "kind": "standard",
        "color": "#8b9bb4",
        "metalness": 0,
        "roughness": 0.7
      },
      "metadata": {}
    }
  ]
}
```

This example is illustrative. The implementation must define numeric bounds, units, angle conventions, defaults, and allowed geometry/material parameters.

## Initial command vocabulary

- `create_object`
- `modify_object`
- `transform_object`
- `delete_object`
- `set_material`
- `duplicate_object`
- `group_objects`
- `camera_action`

Each command must have a typed payload, and object-targeting commands must verify that the target exists. Commands should return a structured success or error result and produce a reversible change record where applicable.

## Execution rules

1. Parse the command.
2. Validate its schema and allowed values.
3. Resolve and validate referenced object IDs.
4. Apply the operation to the canonical scene model.
5. Validate the resulting scene invariants.
6. Record the operation for history.
7. Notify the renderer of the scene change.

Never execute arbitrary code returned by an AI model. Never treat raw model text as a scene operation without parsing and validation.
