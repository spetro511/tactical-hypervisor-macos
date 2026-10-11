# Repository Agent Directives: Tactical Hypervisor (macOS / Swift 6)

## Architectural Constraints
1. **Swift 6 Strict Concurrency**: All state must adhere to Swift 6 complete concurrency checking (`SWIFT_STRICT_CONCURRENCY=complete`). Use `actor` for shared mutable state and mark types `Sendable`.
2. **Zero Chat/AI Tropes in Output**: Do not introduce conversational text, markdown conversational preambles, or conversational fallback UI. All UI and output must adhere to avionics brevity conventions.
3. **Dependency Rules**:
   - `TacticalCore` must remain pure Swift with no AppKit or UI dependencies.
   - `TacticalAudioSVS` uses `AVFoundation` and `CoreAudio` exclusively.
   - `TacticalUI` uses AppKit and MetalKit.
4. **Testing Invariant**: Every actor state transition must have an accompanying deterministic XCTest in `Tests/TacticalCoreTests`.
