# Release Notes

## 2026-04-03 — Menu stability and repository hygiene update

### Highlights
- **Menu value rendering is now safer and more consistent.**
  - Menu items that can contain either plain strings or object values (`{ label, description }`) are now normalized before rendering.
  - This removes unsafe rendering paths and reduces runtime edge-cases when switching between value types.
- **List item refs are now assigned in a stable, index-based way.**
  - Ref handling in the menu list has been hardened to avoid unsafe assignments and stale reference behavior.
  - This improves focus/scroll reliability while navigating menu items.
- **Tooltip description logic is now type-safe.**
  - Tooltip text for selected menu values now uses guarded access for object descriptions.
  - Prevents invalid property access when the selected value is a string.
- **Repository noise has been reduced.**
  - Added ignores for JavaScript/TypeScript dependency folders, compile caches, package-manager debug logs, and frontend build/cache output.

### Technical summary
- Updated:
  - `web/src/features/menu/list/ListItem.tsx`
  - `web/src/features/menu/list/index.tsx`
  - `.gitignore`

### Validation performed
- Frontend build check (`npm run build` in `web/`) completed successfully.

