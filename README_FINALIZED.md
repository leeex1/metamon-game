# Metamon Survival Rogue - Finalized Game

## 🧭 Canonical project context

| | |
| :--- | :--- |
| **This repo** | Metamon Survival Rogue — 2.5D pixel-art roguelike built with the Quillan toolchain. |
| **Canonical package** | Three deployed models: Quillan-Ronin Flagship (~1B), Quillan-Ronin-Mini (~0.8B) and Quillan-Dragon (~1B). The ONI Python sources are implementation/training only. |
| **Donor design** | Flagship and Mini: Qwen 0.6B + Llama ~1B + BitNet 2B-4T + Falcon3 ~1B **as a group** (cross-match fix in progress). Dragon: Falcon3 with an Ollama system message running Quillan's system prompt. |
| **Reading the scores** | The 95–100% table in the root README is **Track A** — the Quillan harness on a third-party frontier base, not a Quillan checkpoint. Hard-exam cells are pending re-test; ARC-AGI-3 public ~99s, private pending. |
| **Historical framing** | Edo period, rōnin and bushidō are real Japanese history and ethics — not roleplay, game mechanics, or fantasy lore. |
| **Canonical docs** | [Root README](https://github.com/leeex1/Quillan-Ronin#readme) · [Fleet model cards](https://github.com/leeex1/Quillan-Ronin/blob/main/docs/MODEL_CARDS.md) |

<!-- QUILLAN-DOCS-PROVENANCE:BEGIN -->
<details>
<summary><b>📌 Quillan documentation provenance</b> — expand for canonical sources</summary>

> **Documentation provenance.** This repo is part of the Quillan-Ronin ecosystem (CrashOverrideX / `leeex1`). Canonical sources live in the root repository: `README.md` (**READ FIRST** — Track A harness-on-frontier vs. Track B native WSP models vs. Track B′ custom Mini) and `docs/MODEL_CARDS.md` (fleet identity, verified facts, open gaps). The large 95–100% benchmark table in the root README is a **harness-on-frontier** result, not a score of any Quillan-owned checkpoint. Creator artifacts (books, music, game demo) have primary-source links in the root README's **Creator and verifiable artifacts** section.  Four-donor design: Flagship and Mini receive all four donors (Qwen ~0.6B + Llama ~1B + BitNet 2B-4T + Falcon3 ~1B) **as a group**; Dragon is Falcon3 with an Ollama system message running Quillan's system prompt. Cross-match fix in progress.  The canonical package is the three deployed models — Quillan-Ronin Flagship (~1B), Quillan-Ronin-Mini (~0.8B) and Quillan-Dragon (~1B); the ONI Python sources are the implementation/training package, not the shipped product. Canonical official links (site, social, repos, Ollama, HF, Grokipedia, NotebookLM, DeepWiki, Genius, YouTube/Suno) are in the root README's **Official links** directory. Historical framing is real Japanese history (Edo period, rōnin, bushidō) used as an ethical reference frame — not roleplay, game mechanics, or fantasy lore.

</details>

<!-- QUILLAN-DOCS-PROVENANCE:END -->

## 🎮 Game Overview

**Metamon Survival Rogue** is a sophisticated 2.5D pixel art roguelike game featuring:
- **30+ unique Metamon** with individual stats and visual designs
- **Modular part system** with 6 part types and 30+ parts
- **Dual game modes**: Adventure RPG and Survival Wave Defense
- **Advanced 3.5D rendering** with perspective, lighting, and particle effects
- **Complete save/load system** with 3 save slots
- **Audio system** with generated sound effects
- **Settings menu** with quality options and preferences
- **Mobile-optimized** with touch controls

## 🚀 Quick Start

### Prerequisites
- **Node.js** 18+ or npm/yarn
- **Modern web browser** (Chrome, Firefox, Safari, Edge)

### Installation & Running
```bash
# Navigate to game directory
cd "Metamon-Survival-Rogue/artifacts/metamon"

# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run serve
```

### Access
- **Development**: http://localhost:3000
- **Production**: Serve the `dist` folder with any web server

## 🎯 Game Features

### Core Gameplay
- **Adventure Mode**: RPG-style exploration with hero classes, Metamon catching, and turn-based battles
- **Survival Mode**: Wave-based defense with auto-attacking Metamon teams
- **30 Metamon Species**: Each with unique stats, elements, and visual designs
- **Modular Parts System**: 6 part types (head, body, arms, legs, tail, weapon) with 30+ parts
- **7 Element Types**: Fire, Water, Grass, Electric, Psychic, Dark, Normal
- **8 Attack Patterns**: Aimed, Spread3/5, Horizontal/Vertical, Radial8, Random, Melee

### Technical Features
- **Advanced Rendering**: 3.5D perspective ground, particle systems, dynamic lighting
- **Spatial Grid Hashing**: Optimized collision detection and performance
- **Object Pooling**: Efficient memory management for projectiles and entities
- **Auto-Save System**: Automatic progress saving with manual save slots
- **Audio System**: Web Audio API with generated sound effects
- **Settings Management**: Persistent user preferences and quality options
- **Mobile Support**: Touch controls and responsive design

## 🛠️ Technical Architecture

### Technology Stack
- **Frontend**: React 18 + TypeScript
- **Build System**: Vite + PostCSS + Tailwind CSS
- **Rendering**: HTML5 Canvas (no external game libraries)
- **Audio**: Web Audio API
- **Storage**: LocalStorage for saves and settings

### Project Structure
```
src/
├── game/                    # Core game engine
│   ├── engine.ts           # Game state and logic
│   ├── renderer.ts         # Canvas rendering system
│   ├── metamon.ts          # Metamon data and templates
│   ├── parts.ts            # Part system and attacks
│   ├── audioManager.ts     # Audio system
│   └── constants.ts        # Game constants
├── pages/                  # UI screens
│   ├── MenuScreen.tsx      # Main menu
│   ├── GameCanvas.tsx      # Game canvas component
│   ├── SettingsScreen.tsx  # Settings menu
│   └── [Other screens...]  # Adventure/UI screens
├── assets/mecha/            # Metamon sprites (30 PNG files)
└── assets/mecha/portraitMap.ts  # Sprite mapping
```

### Key Systems

#### Save/Load System
- **3 Save Slots**: Manual saving with automatic fallback
- **Auto-Save**: Progress saved after each round
- **Persistent Storage**: LocalStorage with JSON serialization
- **Version Compatibility**: Save format includes version tracking

#### Audio System
- **Generated Sounds**: Web Audio API synthesis for beeps and effects
- **Context Management**: Browser-compliant audio initialization
- **Volume Control**: Master volume with individual sound control
- **Performance**: Efficient audio buffer management

#### Settings System
- **Quality Options**: Low/Medium/High graphics settings
- **Audio Controls**: Volume adjustment and mute options
- **Game Preferences**: Auto-save toggle, particle effects toggle
- **Persistent Storage**: Settings saved to LocalStorage

## 🎮 Game Controls

### Desktop
- **Arrow Keys/WASD**: Movement (Survival mode)
- **Mouse**: Menu navigation and UI interaction
- **Space/Enter**: Confirm actions
- **Escape**: Cancel/Back

### Mobile
- **Touch Joystick**: Movement control (Survival mode)
- **Touch Buttons**: All UI interactions
- **Swipe Gestures**: Menu navigation

## 📊 Performance Metrics

### Build Optimization
- **Bundle Size**: ~270KB (gzipped ~83KB)
- **Asset Loading**: 30+ Metamon sprites (~2.4MB total)
- **Frame Rate**: Target 60fps with adaptive quality
- **Memory Usage**: Efficient object pooling and cleanup

### Quality Settings
- **Low**: Reduced particles, basic effects
- **Medium**: Balanced performance and visuals
- **High**: Full effects, maximum quality

## 🔧 Development

### Build Commands
```bash
npm run dev          # Development server
npm run build        # Production build
npm run serve        # Preview production build
npm run typecheck    # TypeScript type checking
```

### File Structure
- `src/game/engine.ts` - Core game logic and state management
- `src/game/renderer.ts` - Canvas rendering and visual effects
- `src/pages/` - React components for UI screens
- `src/assets/mecha/` - Game sprites and assets
- `dist/` - Production build output

### Adding New Content
- **Metamon**: Add to `metamon.ts` templates and include sprite
- **Parts**: Extend `parts.ts` with new part definitions
- **Sounds**: Add to `audioManager.ts` generated sounds
- **UI**: Create new screen components in `pages/`

## 🐛 Troubleshooting

### Common Issues
- **Audio Not Working**: Requires user interaction to initialize (browser security)
- **Build Fails**: Check Node.js version and clear node_modules
- **Sprites Not Loading**: Verify asset paths in `spriteCache.ts`
- **Save System Issues**: Check LocalStorage permissions and quota

### Performance Tips
- Use **Medium** quality for older devices
- Disable **particles** if experiencing lag
- Close other browser tabs for better performance
- Use **Chrome** for best compatibility

## 📝 License

This is a finalized game project for local deployment and educational purposes.

## 🎯 Final Status

✅ **PRODUCTION READY** - All core features implemented and tested
✅ **Windows Compatible** - Cross-platform build system
✅ **Mobile Optimized** - Touch controls and responsive design
✅ **Feature Complete** - Save/load, audio, settings, all game modes
✅ **Performance Optimized** - Efficient rendering and memory management
✅ **Documentation Complete** - Comprehensive setup and development guide

---

**Game is ready for immediate local deployment and gameplay!** 🚀
