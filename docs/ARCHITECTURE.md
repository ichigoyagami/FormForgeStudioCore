# Architecture

FormForge uses Blender as its GPL engine foundation while keeping FormForge-owned workflow code clearly separated and reviewable.

## Layers

1. **Upstream engine** — pinned Blender source revision.
2. **Native integration** — C/C++ patches for branding, startup, keymaps, modelling and retopology behaviour.
3. **Built-in workflow modules** — bundled Python UI and tool orchestration under `scripts/addons_core`.
4. **Branding** — original FormForge icon, splash and theme assets.
5. **Packaging** — Windows installer and portable build.
6. **Validation** — patch checks, Python compilation, smoke tests and later interaction tests.

Native topology code should live in dedicated FormForge modules instead of accumulating in a single UI add-on. Experimental behaviour must be feature-gated until it passes repeatable viewport and undo tests.

