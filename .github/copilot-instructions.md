# Workspace Instructions

## Project Overview

- This repository is a small Vite + React 19 + TypeScript app for a social bingo game.
- Styling is done with Tailwind CSS v4 through `src/index.css` using `@import 'tailwindcss'` and `@theme` tokens.
- The playable app lives under `src/`.
- Ignore `workshop/` unless the user explicitly asks about the lab materials.
- Do not assume Astro conventions here. This repo does not use Astro.

## Commands

- Install dependencies: `npm install`
- Start dev server: `npm run dev`
- Run lint: `npm run lint`
- Run tests: `npm run test`
- Build production bundle: `npm run build`

## Architecture

- `src/main.tsx` bootstraps the React app.
- `src/App.tsx` switches between the start screen and game screen and mounts the bingo modal.
- `src/hooks/useBingoGame.ts` is the main state boundary. Keep game flow, persistence, and interaction logic here.
- `src/utils/bingoLogic.ts` contains pure bingo logic. Prefer adding or changing rules here and covering them with tests.
- `src/components/` contains presentational UI pieces such as the board, squares, modal, and screens.
- `src/types/` contains shared domain types.
- `src/data/questions.ts` is the content source for bingo prompts.

## Working Conventions

- Prefer small, focused changes that preserve the current component and hook structure.
- Put business rules in `src/utils/` or the game hook, not directly inside presentational components.
- When changing bingo rules or board behavior, update `src/utils/bingoLogic.test.ts`.
- Preserve localStorage compatibility in `useBingoGame` unless the task explicitly allows resetting persisted state.
- Follow the existing TypeScript style and keep types explicit at module boundaries.

## Styling

- Follow the Tailwind v4 setup already in the repo.
- Reuse or extend theme tokens in `src/index.css` before scattering one-off color values.
- Keep the UI mobile-friendly; the app is designed like a lightweight touch-first experience.
- Preserve existing visual patterns unless the user asks for a redesign.

## Agent Notes

- Link to existing docs instead of duplicating them. Start with `README.md` for setup.
- `CONTRIBUTING.md` is standard Microsoft OSS guidance; do not duplicate it into feature work.
- If a request mentions Astro, verify it first and correct the assumption before editing code or instructions.
