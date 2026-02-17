# Arcades

Arcades is a SwiftUI iOS app that bundles a couple of casual games behind a light onboarding flow. Users enter a name (shared across views) and then choose between a memory matching game and a simplified checkers experience.

## Features
- SwiftUI app targeting iOS 16.1+ with Xcode project included.
- Onboarding screen that collects a user name (min 5 characters) and shares it across the app via `NameTracker`.
- Game picker that routes to either Memory or Checkers.
- Memory Game: 6 pairs of dog-breed images, flip-to-match mechanics, 60s timer with visual state changes, restart button, and progress indicator.
- Checkers: basic board with draggable tokens, pinch-to-zoom on the board, 10-minute timer with visual cues, and a restart action.
- Themed assets and background images stored in `Assets.xcassets`.

## Requirements
- Xcode 15+ (or newer) with Swift 5.9 toolchain.
- iOS Simulator or device running iOS 16.1 or later.

## Getting Started
1. Open `arcades.xcodeproj` in Xcode.
2. Select the `arcades` scheme and an iOS simulator (16.1+ recommended).
3. Run the project (`⌘R`).

## Gameplay
1. Home: enter a user name (minimum 5 characters) and tap **Continue**.
2. Game Picker: choose **Memory Game** or **Checkers**.
3. Memory Game:
   - Tap cards to flip and find matching pairs.
   - Timer bar changes color and resets on restart.
4. Checkers:
   - Drag tokens on the board (won pieces can be moved to the side zones).
   - Pinch to zoom the board.
   - Timer bar changes color and resets on restart.

## Project Structure
- `arcades/arcadesApp.swift` — app entry point.
- `arcades/HomePageView.swift` — onboarding and name capture.
- `arcades/ChooseAGame.swift` — game selection view.
- `arcades/Memory Game/` — memory game logic (`MemoryGame.swift`), view model (`MemoryGameFramework.swift`), and UI (`MemoryGameContentView.swift`).
- `arcades/Checkers Game/` — checkers state (`CheckersGameFrameWork.swift`), board pieces (`UnitMaker.swift`), and UI (`CheckersContentView.swift`).
- `arcades/Player Name Tracker/` — shared name state (`NameTracker.swift`).
- `Assets.xcassets` — game art and backgrounds.
- `screenshots/` — place to store captures of the app (if available).

## Notes
- No external dependencies are required beyond SwiftUI.
- If assets appear blank, confirm `Assets.xcassets` is included in the target membership.
