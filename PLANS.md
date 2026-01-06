# ShadowAI iOS Port - Strategic Plan

## Vision
To bring the "Unified Shadow" experience to iOS, focusing on high-performance SSH connectivity, cloud synchronization, and voice-first interaction.

## Tech Stack (MVP)
- **Language:** Swift 6 (Strict Concurrency)
- **UI:** SwiftUI (Material 3 Expressive theme replication)
- **Architecture:** MVVM + Coordinator Pattern
- **Networking:** `Network.framework` for TCP Signaling, `Shout` (libssh2) for SSH.
- **Persistence:** SwiftData

## Phase 1: MVP Core (Current Focus)
1. **SSH Roaming Engine:** Port `ShadowConnectionManager` logic for persistent backend connection.
2. **Unified Sync:** Implement `CentralSyncManager` for Projects, Notes, and Chats.
3. **Voice UI:** SwiftUI implementation of the asymmetric chat bubbles and red-themed conversational dialog.
4. **ShadowBridge Link:** Discovery of local PC backends via mDNS.

## Deferred Features (Post-MVP)

### 1. Local LLM (llama.cpp)
**Status:** DEFERRED
- **Reasoning:** High initial complexity for Swift/C++ interop, significant binary size increase, and high thermal impact on mobile. 
- **Plan:** Initially rely on SSH-linked backends (Claude Code, Gemini CLI) or the Central Cloud API.

### 2. CarPlay Support
**Status:** DEFERRED
- **Reasoning:** Requires Apple's explicit CarPlay entitlement approval (Assistant/IOT category), which can take weeks/months.
- **Plan:** Focus on a rock-solid handheld experience first. CarPlay templates will be mapped to the `Talk` tab logic once the app is stable and entitlements are requested.

## Key Parity Requirements
- **Encryption:** Must use Keychain for all sensitive credentials (API tokens, SSH keys).
- **Theme:** Replicate the 2px border-radius technical look and Claude Terracotta accent (#D97757).
- **Roaming:** Maintain the UDP Signaling logic to handle NAT traversal and IP changes seamlessly.
