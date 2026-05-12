# CLAUDE.md

Guidance for Claude Code when working in this repository.

## Project
Personal art gallery for Dalia Landau. Single file: `index.html`. Images in `images/` (169 JPG files, many with Hebrew names).

## Rules — never break these
- All images must use `object-fit: contain` (never `cover`) — no cropping allowed
- Lightbox arrows are `position: absolute` inside the fixed lightbox: `#lb-prev { left: 24px }` / `#lb-next { right: 24px }` — do not change to flex layout
- All folders in the `folders` array must use `allPaintings.filter(...)` — never hardcode `paintings: []`
- Hebrew filenames need URL-encoding in `src` — use `[Uri]::EscapeDataString()` in PowerShell to generate them
- To check for duplicate image files, use Node.js crypto — PowerShell `Get-FileHash` gives wrong results with Hebrew filenames

## Memory
- Update `C:\Users\8land\.claude\projects\c--Users-8land-projects-DaliaLandausGallery\memory\project_gallery.md` whenever folder contents or image count changes
- Always save session progress to memory — user was very frustrated losing context between sessions
