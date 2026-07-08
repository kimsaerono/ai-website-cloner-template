<!-- BEGIN:nextjs-agent-rules -->
# This is NOT the Next.js you know

This version has breaking changes — APIs, conventions, and file structure may all differ from your training data. Read the relevant guide in `node_modules/next/dist/docs/` before writing any code. Heed deprecation notices.
<!-- END:nextjs-agent-rules -->

# Website Reverse-Engineer Template

## What This Is
A reusable template for reverse-engineering any website into a clean, modern codebase using AI coding agents. Supports **Vue (Vite)** and **React (Next.js)** frameworks. Just run `/clone-website [--framework vue|react] <url1> [<url2> ...]`.

## Tech Stack

### Vue (Default)
- **Framework:** Vite 6 + Vue 3 + Vue Router 4 (TypeScript strict)
- **UI:** shadcn-vue (Radix-vue primitives, Tailwind CSS v4, `cn()` utility)
- **Icons:** Lucide Vue Next (default — will be replaced/supplemented by extracted SVGs)
- **Styling:** Tailwind CSS v4 with oklch design tokens
- **Deployment:** Vercel / Netlify / Static hosting

### React
- **Framework:** Next.js 16 (App Router, React 19, TypeScript strict)
- **UI:** shadcn/ui (Radix primitives, Tailwind CSS v4, `cn()` utility)
- **Icons:** Lucide React (default — will be replaced/supplemented by extracted SVGs)
- **Styling:** Tailwind CSS v4 with oklch design tokens
- **Deployment:** Vercel

### Shared
- **Template location:** `templates/react/` or `templates/vue/`
- **Asset storage:** `public/images/`, `public/videos/`, `public/seo/`
- **Research output:** `docs/research/`, `docs/design-references/`

## Commands
Run commands from within the selected framework directory (`templates/react/` or `templates/vue/`):
- `npm run dev` — Start dev server
- `npm run build` — Production build
- `npm run lint` — ESLint check
- `npm run typecheck` — TypeScript check
- `npm run check` — Run lint + typecheck + build

## Code Style
- TypeScript strict mode, no `any`
- Named exports, PascalCase components, camelCase utils
- Tailwind utility classes, no inline styles
- 2-space indentation
- Responsive: mobile-first

## Design Principles
- **Pixel-perfect emulation** — match the target's spacing, colors, typography exactly
- **No personal aesthetic changes during emulation phase** — match 1:1 first, customize later
- **Real content** — use actual text and assets from the target site, not placeholders
- **Beauty-first** — every pixel matters

## Project Structure
```
templates/
  react/                    # React template (Next.js 16)
    src/
      app/                  # Next.js App Router routes
      components/
        ui/                 # shadcn/ui primitives
        icons.tsx           # Extracted SVG icons as React components
      lib/utils.ts          # cn() utility (shadcn)
      types/                # TypeScript interfaces
      hooks/                # Custom React hooks
    public/                 # Downloaded assets
    package.json            # Dependencies & scripts

  vue/                      # Vue template (Vite 6)
    src/
      assets/main.css       # Global styles with Tailwind CSS v4
      components/
        ui/                 # shadcn-vue primitives
        icons/              # Extracted SVG icons as Vue SFCs
      lib/utils.ts          # cn() utility (shadcn)
      views/                # Vue Router page views
      router/index.ts       # Route definitions
      App.vue               # Root component
      main.ts               # Entry point
    public/                 # Downloaded assets
    index.html              # HTML entry point
    package.json            # Dependencies & scripts

docs/
  research/                 # Inspection output (design tokens, components, layout)
  design-references/        # Screenshots and visual references
scripts/                    # Asset download scripts
```

## MOST IMPORTANT NOTES
- When launching Claude Code agent teams, ALWAYS have each teammate work in their own worktree branch and merge everyone's work at the end, resolving any merge conflicts smartly since you are basically serving the orchestrator role and have full context to our goals, work given, work achieved, and desired outcomes.
- After editing `AGENTS.md`, run `bash scripts/sync-agent-rules.sh` to regenerate platform-specific instruction files.
- After editing `.claude/skills/clone-website/SKILL.md`, run `node scripts/sync-skills.mjs` to regenerate the skill for all platforms.

@docs/research/INSPECTION_GUIDE.md