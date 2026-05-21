# Repository Guidelines

## Project Structure & Module Organization

This is a Vue 3 + TypeScript application built with Vite. Source code lives in `src/`, with entry points in `src/main.ts` and `src/App.vue`. Shared styling is in `src/style.css`.

Components are organized by feature under `src/components/`, including `TreePanel/`, `ConclusionPanel/`, and `GraphShared/`. Reusable composition logic belongs in `src/composables/`, domain types in `src/types/`, and pure helpers in `src/utils/`. Static public files belong in `public/`; imported assets belong in `src/assets/`. Build output is generated in `dist/` and should not be edited directly.

## Build, Test, and Development Commands

- `npm run dev`: starts the Vite development server with hot reload.
- `npm run build`: runs `vue-tsc -b` for type checking, then builds production assets with Vite.
- `npm run preview`: serves the built `dist/` output locally for verification.

Run commands from the repository root. Dependencies are locked in `package-lock.json`, so use `npm install` when refreshing local packages.

## Coding Style & Naming Conventions

Use Vue single-file components with `<script setup lang="ts">` where practical. Keep component filenames in PascalCase, such as `DocumentView.vue`, and composables in camelCase with a `use` prefix, such as `useDataLoader.ts`. Type files should describe domain areas, such as `operator.ts`.

Follow the existing TypeScript style: two-space indentation, semicolon-free code, and focused modules. Prefer typed props, emits, and helper return values over implicit `any`. Put shared UI logic in composables instead of duplicating state across components.

## Testing Guidelines

No automated test framework is currently configured. For now, validate changes with `npm run build` and manual browser checks through `npm run dev` or `npm run preview`.

When adding tests, place them near the code they cover using `*.test.ts` or `*.spec.ts`. Prefer Vitest with Vue Test Utils. Cover parsing utilities, composables, and component behavior with non-trivial state transitions.

## Commit & Pull Request Guidelines

Recent history uses brief messages such as `debug` and `static data`; use more descriptive messages going forward. Prefer imperative commits like `Add annotation parser guard`.

Pull requests should include a short summary, verification commands, linked issues when applicable, and screenshots or recordings for UI changes. Keep changes scoped to one concern and call out any data shape or API assumptions.

## Agent-Specific Instructions

Do not edit generated `dist/` files unless explicitly requested. Preserve existing user changes, keep patches narrow, and run `npm run build` before finalizing code changes when feasible.
