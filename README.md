# physics

Physics integration experiments for native React Native games and 3D apps.

This repository is a reserved public shell. It does not yet contain migrated production code.

## Intended Scope

- Native-friendly physics architecture for React Native games
- Rapier replacement or bridge investigations that avoid native WASM assumptions
- Deterministic simulation boundaries that can be tested through E2E flows
- Shared primitives for Sortessori and future games

## Non-Goals

- Committing to a public physics API before native constraints are validated
- Wrapping browser-first physics code without a real native strategy
- Rebuilding game-specific logic in this shared package prematurely