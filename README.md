# Arcades

**Arcades** is a lightweight SwiftUI iOS mini‑arcade: enter a player name once, pick a game, and start playing in seconds.

- **Example inputs**:
  - **Name**: “Jordan” → **Continue**
  - **Pick**: **Memory Game** → tap to match dog-breed cards
  - **Pick**: **Checkers** → drag pieces on a pinch‑zoomable board

## Why Arcades

Casual games are best when the “setup” is basically zero. Arcades keeps the flow simple:

- **Fast start**: minimal onboarding, no accounts, no backend required
- **Two games, one shell**: a single home → game picker → gameplay loop
- **Personal touch**: the same player name follows you into each game

## What you can do

- **Memory Game**: match **6 pairs** of dog‑breed cards with a countdown timer, restart, and a simple progress indicator
- **Checkers (simplified)**: a casual checkers-style board with **draggable pieces** and **pinch‑to‑zoom**

## Demo flow

### 1) Start a session

- **You**: enter a name (minimum **5** characters) and tap **Continue**
- **Arcades**: validates the name and stores it as shared app state
- **You get**: a personalized welcome + your name shown inside the games

### 2) Pick a game

- **You**: choose **Memory Game** or **Checkers**
- **Arcades**: routes you to the selected game with the same player context
- **You get**: a consistent “mini‑arcade” experience across both games

## How to play

- **Memory Game**: tap to flip cards → find matching pairs → restart anytime
- **Checkers (simplified)**: drag pieces around the board → pinch to zoom in/out

## Quickstart

### Requirements

- **macOS** with **Xcode 15+** (Swift 5.9)
- **iOS 16.1+** simulator or device

### Run in Xcode

1. Open `arcades.xcodeproj`
2. Select the `arcades` scheme and an iOS simulator/device (iOS 16.1+)
3. Run (`⌘R`)

### Build from the command line (smoke check)

```bash
xcodebuild \
  -project arcades.xcodeproj \
  -scheme arcades \
  -destination 'generic/platform=iOS Simulator' \
  clean build
```

## Screenshots

<p>
  <img src="screenshots/arcades_screenshot_1.png" width="220" alt="Onboarding" />
  <img src="screenshots/arcades_screenshot_2.png" width="220" alt="Game picker" />
</p>
<p>
  <img src="screenshots/arcades_screenshot_4.png" width="220" alt="Memory game" />
  <img src="screenshots/arcades_screenshot_3.png" width="220" alt="Checkers" />
</p>

## Technical architecture (high level)

- **SwiftUI app shell**
  - Entry point: `arcades/arcadesApp.swift`
  - Onboarding: `arcades/HomePageView.swift`
  - Game picker: `arcades/ChooseAGame.swift`
- **Shared state**
  - `NameTracker` is injected as an environment object so the player name is available across views.
- **Memory Game**
  - Model: `arcades/Memory Game/MemoryGame.swift`
  - View model: `arcades/Memory Game/MemoryGameFramework.swift`
  - UI: `arcades/Memory Game/MemoryGameContentView.swift`
- **Checkers (simplified)**
  - State: `arcades/Checkers Game/CheckersGameFrameWork.swift`
  - Board/pieces model: `arcades/Checkers Game/UnitMaker.swift`
  - UI: `arcades/Checkers Game/CheckersContentView.swift`
- **Assets**
  - Art/backgrounds live in `arcades/Assets.xcassets`
  - README screenshots live in `screenshots/`

## Production readiness notes

- **Offline-first**: no network calls and no external runtime dependencies beyond SwiftUI/Combine
- **CI build**: GitHub Actions runs `xcodebuild ... clean build` on macOS for each PR/push
- **Validation**: the onboarding flow enforces a minimum name length before proceeding
- **Known scope**: checkers is intentionally **simplified** (casual/freeform piece movement rather than full rules enforcement)
- **Common failure mode**: if images render blank, confirm `Assets.xcassets` is included in target membership

## Use cases

- A small SwiftUI sample app to learn navigation + shared state
- A starter project for adding more mini‑games behind a picker
- A reference for timers, simple animations, and gesture handling (tap/drag/pinch)

## Contributing

See `CONTRIBUTING.md` for local setup and PR guidelines.

## License

MIT. See `LICENSE`.

Arcades is intentionally small and hackable—an easy place to learn SwiftUI patterns and build out a bigger mini‑arcade.
