# physics

Physics integration experiments for native React Native games and 3D apps.

This repository is a reserved public shell. It does not yet contain migrated production code.

## Intended Scope

- Native-friendly physics architecture for React Native games
- Rapier replacement or bridge investigations that avoid native WASM assumptions
- Deterministic simulation boundaries that can be tested through E2E flows
- Shared primitives for Sortessori and future games

## Migration Handoff

Sortessori is the reference app for the first physics migration slice. The current source
of truth is `../sortessori/docs/unruly-systems-migration-plan.json`, backed by
`../sortessori/docs/webgpu-cutover-audit.md`.

Import gate: physical iOS cutover evidence verified and package-boundary checks green.

Import production code here only after the Sortessori iOS WebGPU cutover has physical
manual evidence for touch, VoiceOver, sensory feedback, and Expo GL rollback, and
`../sortessori` passes:

```bash
bun run ci
bun run verify:webgpu-cutover
bun run verify:package-boundaries
```

The first eligible slice is the native physics boundary now tracked as
`@unrulysystems/physics-native`. Keep the API private until the next implementation
decides whether broader Rapier APIs, raycasts, larger worlds, Android parity, or
high-frequency reads require JSI or TurboModule instead of the current synchronous bridge.

## Non-Goals

- Committing to a public physics API before native constraints are validated
- Wrapping browser-first physics code without a real native strategy
- Rebuilding game-specific logic in this shared package prematurely
