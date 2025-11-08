# Biometric Keychain
#### Your private key, unlocked by you.

## Overview
Biometric Keychain is a privacy-first identity system that makes biometric authentication visible, controllable, and reusable across apps. Rather than treating Face ID or fingerprint unlock as just a phone feature, this project frames them as a local encrypted key manager that apps can use to verify presence and sign sensitive actions.

## What it does
It provides a device-first credential manager that:
🔓 Unlocks private keys with biometrics (Face ID, fingerprint).
✉️ Signs app requests locally (e.g., bank transfer approvals).
 🪪 Shows a consent log of biometric authorizations.
🧩 Defines per-app policy rules (e.g., require biometric for transfers > ₦100,000).

## 💡 Why it matters
Users already rely on biometrics but lack transparency and control. Biometric Keychain gives people clear visibility into when their biometric approval is used and provides safer, passwordless flows for high-risk actions.

## Who it's for
👤 Privacy-conscious users
🏦 Fintech & HealthTech app developers
🧠 Organizations reducing password & OTP reliance

## Key features
- Secure Enclave / Keystore key generation
- Biometric gating and one-tap approvals
- Consent log and session management
- Developer SDK for signing assertions

## Tech preview
💻 On-device: Secure Enclave (iOS) / Android Keystore
🛠️ Standards: WebAuthn / FIDO2 patterns
🔐 Demo stack: React (frontend) + Node.js (backend demo)

 💻  On-device: Secure Enclave (iOS) / Android Keystore
 🛠️  Standards: WebAuthn / FIDO2 patterns







⭐ **HNG Stage 4A Submission**  
Built with ❤️ by **Blessing Owobi**  
November, 2025
