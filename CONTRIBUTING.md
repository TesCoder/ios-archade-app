## Contributing

Thanks for taking the time to contribute!

## Development setup
- **Requirements**: macOS with **Xcode 15+** (Swift 5.9) and an iOS 16.1+ simulator/device.
- **Open**: `arcades.xcodeproj`
- **Run**: select the `arcades` scheme, then `⌘R`

## Smoke check (build)
Before opening a PR, make sure the project builds from a clean checkout:

```bash
xcodebuild -project arcades.xcodeproj -scheme arcades -destination 'generic/platform=iOS Simulator' build
```

## Making changes
- Keep PRs small and focused.
- Prefer self-contained SwiftUI views and clear naming.
- Avoid committing user-specific Xcode files (`xcuserdata`, `.xcuserstate`, etc.).

## Submitting a pull request
- Create a feature branch from `main`.
- Describe **what changed** and **why**.
- Include screenshots/GIFs for UI changes when possible.

## Reporting bugs / requesting features
Please open an issue with:
- What you expected vs what happened
- Steps to reproduce
- Xcode/iOS versions and device/simulator details
