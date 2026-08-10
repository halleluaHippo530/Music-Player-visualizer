# CityTone Release Notes

## v5.6.0 — Jungle Theme Complete Redraw + Aztec Temples

**Release Date:** 2026-08-10

### Highlights

- **Complete jungle theme redraw**: Every terrain function rewritten to use smooth `quadraticCurveTo` path rendering, matching cityscape's approach exactly
- **Aztec stepped pyramid temples**: All jungle temples redesigned as Mesoamerican stepped pyramids with volumetric shading, central stairways, and stone block textures
- **Disco ball test module removed**: Cleaned up `disco-ball-test.html` from the package

### What's New

#### Jungle Theme — Cityscape-Style Rendering (v5.6.0)

All jungle terrain functions rewritten from column-based `fillRect` to smooth `quadraticCurveTo` paths:

| Function | Change |
|----------|--------|
| `drawMountains()` | Smooth ridge paths with 120 control points, gradient fills, sunlit crest strokes |
| `drawTropicalMountains()` | Smooth paths for haze ridges and tropical ridges |
| `drawRiver()` | Precomputed wave point arrays with smooth path fill, sky reflection, crest highlights |
| `drawFarForest()` | Smooth path fill with gradient, replacing per-column fillRect |
| `drawMidfarForest()` | Smooth path fill with quadraticCurveTo |
| `drawGround()` | Far bank, earth, and flood overflow all use smooth paths |

#### Aztec Temple Redesign (v5.6.0)

- `drawRemoteTemples()`: Stepped pyramids with alternating stone tones, volumetric shading, central stairways, moss on step edges
- `drawAztecPyramids()`: Detailed pyramids with perspective scaling, carved glyph embossments, serpent head carvings, aborigines with firelight at night
- `drawAztecStatue()`: Tall stone figure with headdress and moss patches
- `drawZumaFrog()`: Round stone frog with bulging eyes and mossy texture

#### Performance — Dual-rAF Eliminated (v5.5.0)

- Jungle visualizer integrated into main `P._loop()` via `JUNGLE.tick(dt)`
- No independent `requestAnimationFrame` loop — eliminates persistent slow-motion bug
- Same dt-based timing as cityscape (clamped 0.25-3.0)

### Package Changes

- **Removed**: `disco-ball-test.html` (test module, no longer needed)
- **Updated**: README.md with v5.5.0/v5.6.0 features and version references
- **Updated**: .gitignore to exclude archived version snapshots (`CityTone_v*/`, `_stage_*/`)
- **Updated**: Development guide with v5.6.0 changelog

### File Structure

```
LaunchPulse.html             Main application (single file, no dependencies)
screenshots/                 Preview images (9 scenes)
citytone-intro/              Intro page with screenshots
development-guide/
  development-guide.html     Version history & changelog (v1.0 - v5.6.0)
  development-manual.html    Architecture, modules, performance guide
  prompt-development-manual.html  AI prompt templates & constraints
README.md                    Project documentation
RELEASE_NOTES.md             This file
LICENSE                      MIT License
.gitignore                   Git ignore rules
```

### Upgrade Notes

- No migration needed — `LaunchPulse.html` is a self-contained single file
- Open in any modern browser (Chrome 80+, Firefox 80+, Safari 14+, Edge 80+)
- No build tools, no dependencies, no installation required

### Previous Release: v5.5.0 (2026-08-09)

- Dual-rAF architecture permanently eliminated
- Jungle integrated into main rendering loop
- Slow-motion bug after repeated play/pause fixed

---

**License:** MIT  
**Repository:** Single-file HTML5 Canvas audio visualizer
