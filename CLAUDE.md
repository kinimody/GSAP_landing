# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

React 19 + Vite landing page for "Velvet Pour" cocktail bar brand. Animation-heavy marketing site using GSAP for scroll and text animations, Tailwind CSS v4 for styling.

## Commands

- `npm run dev` — Start Vite dev server with HMR
- `npm run build` — Production build (outputs to `dist/`)
- `npm run lint` — Run ESLint
- `npm run preview` — Preview production build locally

No test framework is configured.

## Architecture

**Stack:** React 19, Vite 7, GSAP 3.14, Tailwind CSS v4 (via `@tailwindcss/vite` plugin), react-responsive

**Entry flow:** `index.html` → `src/main.jsx` → `src/App.jsx`

**Key directories:**
- `src/components/` — React components (Navbar, Hero, etc.)
- `src/constants/index.js` — All static data (nav links, cocktail lists, etc.)
- `public/fonts/`, `public/images/`, `public/videos/` — Static assets

**Page sections** (defined in App.jsx/CSS): hero, cocktails, about, art, menu, contact

## Key Patterns

**GSAP animations** use the `useGSAP` hook from `@gsap/react` for automatic cleanup. ScrollTrigger and SplitText plugins are used for scroll-based and text-splitting animations. Animations are typically defined inside `useGSAP(() => { ... }, [])`.

**Tailwind CSS v4** configuration lives in `src/index.css` using `@theme` (custom colors, fonts) and `@utility` (custom utilities like `flex-center`, `text-gradient`, `col-center`, `abs-center`). There is no `tailwind.config.js` — everything is inline.

**Custom fonts:** Mona Sans (body), Modern Negra (display/headings), DM Serif Text (decorative)

**Custom colors:** `yellow: #e7d393`, `white-100: #efefef`, black background throughout

**ESLint** uses flat config format (`eslint.config.js`). Unused vars starting with uppercase or underscore are allowed.
## Git Workflow

### Branching
- Always create a new branch before making changes; never commit to main
- Branch naming: `feat/short-description`, `fix/bug-name`, `refactor/what-changed`

### Commits
- Use conventional commits format: `feat:`, `fix:`, `docs:`, `refactor:`, `test:`
- Write commit messages in present tense: "add login form" not "added login form"
- Keep commits atomic — one logical change per commit

### Pull Requests
- Always push to a branch and open a PR; never push directly to main
- PR titles follow the same conventional commit format
- Run tests before committing: `npm test`
- Run typecheck before committing: `npm run typecheck`

## Git Safety Rules
- NEVER push directly to main or master
- NEVER force push (git push --force) without explicit permission
- ALWAYS run tests before committing: npm test
- ALWAYS run typecheck before committing: npm run typecheck
- If tests fail, fix them before committing — do not commit broken code
- Ask for confirmation before opening a PR


