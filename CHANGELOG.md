# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.4.0] - 2026-07-07

### Added
- Vue template (Vite 6 + Vue 3 + shadcn-vue) as default framework
- React template (Next.js 16 + React 19 + shadcn/ui) as alternative framework
- `--framework vue|react` flag in `/clone-website` skill
- `skills/clone-website/SKILL.md` for `npx skills add` support
- Dual-framework CI pipeline (GitHub Actions)

### Changed
- Default framework changed from React to Vue
- Author and copyright updated to kimsaerono
- README updated for dual-framework Quick Start
- CI workflow updated to test both Vue and React templates
- Copilot setup steps updated for dual-framework structure