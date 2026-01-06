# ShadowAI iOS Port - Strategic Plan

## Vision
To bring the "Unified Shadow" experience to iOS, focusing on high-performance SSH connectivity, cloud synchronization, and voice-first interaction.

## Tech Stack (MVP)
- **Language:** Swift 6 (Strict Concurrency)
- **UI:** SwiftUI (Native iOS HIG with Shadow Technical Accents)
- **Architecture:** MVVM + Coordinator Pattern
- **Networking:** `Network.framework` for TCP Signaling, `Shout` (libssh2) for SSH.
- **Persistence:** SwiftData

## Phase 1: MVP Core (Current Focus)
1. **SSH Roaming Engine:** Port `ShadowConnectionManager` logic for persistent backend connection.
2. **Unified Sync:** Implement `CentralSyncManager` for Projects, Notes, and Chats.
3. **Voice UI:** Native SwiftUI implementation using `SF Symbols` and standard iOS conversational patterns.
4. **ShadowBridge Link:** Discovery of local PC backends via mDNS (Bonjour).

## Deferred Features (Post-MVP)

### 1. Local LLM (llama.cpp)
**Status:** DEFERRED
- **Reasoning:** High initial complexity for Swift/C++ interop, significant binary size increase, and thermal impact. 
- **Plan:** Initially rely on SSH-linked backends or Cloud APIs.

### 2. CarPlay Support
**Status:** DEFERRED
- **Reasoning:** Requires Apple's explicit CarPlay entitlement approval.
- **Plan:** Focus on handheld experience first.

## Key Parity Requirements
- **Encryption:** Must use Keychain for all sensitive credentials.
- **Native Aesthetic:** Support for Dynamic Type, SF Symbols 6, and proper dark mode materials.
- **Theme:** Retain the Claude Terracotta accent (#D97757) but apply it via native iOS tinting.
- **Roaming:** Maintain the UDP Signaling logic to handle NAT traversal and IP changes.
