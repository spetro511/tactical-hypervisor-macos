# Project Context: Tactical Hypervisor Bridge

- Language: Swift 6 (macOS Native target), Python 3.11+ (FastAPI Telemetry Bridge)
- Test Command: `swift test`
- Build Command: `swift build`
- Style Guide: No force unwrapping (`!`), explicit error handling with custom `Error` enums, memory alignment checks on raw pointers.

Configure custom slash commands in .opencode/commands/verify-actor.md:

Run the Swift test suite for the interlock actor:
```bash
swift test --filter HardwareInterlockGateTests


If failures occur, read the compiler and assertion outputs, locate the state regression in Sources/TacticalCore/InterlockEngine.swift, and resolve it without breaking Sendable constraints.