#  Biometric Keychain — System Architecture

## 🧩System summary
Biometric Keychain is a device-native credential manager and lightweight SDK for apps. It keeps private keys on-device, gated by biometrics, and issues signed assertions for sensitive actions. Servers verify these assertions before performing the requested operation.

## 🧠Components
1. **Frontend (SDK)** 🖥️
   - API: `BiometricKeychain.sign({ appId, action, amount, nonce })`  
   - Responsibilities: UI prompt for biometric, request assembly, signed token submission, consent log display.

2. **On-device Secure Layer** 📱
   - Secure Enclave (iOS) / Android Keystore  
   - Key generation, local signing, no export of private keys.

3. **Backend Verification Server** ☁️ 
   - Verifies signatures using public key/attestation.  
   - Records logs and handles revocation.  
   - Tech stack (demo): Node.js + Express + PostgreSQL.

4. **Database (example tables)** 🗄️ 
   - `users`: id, device_id, public_key, created_at  
   - `logs`: id, user_id, action, timestamp, signature  
   - `revocations`: id, user_id, key_id, reason, created_at

## Communication flow
1. App constructs unsigned payload: `{ appId, action, amount, nonce }`.  
2. SDK prompts user biometric verification.  
3. On success, secure enclave signs payload → returns signed token.  
4. SDK sends signed token to the backend.  
5. Backend validates signature + attestation → executes action if valid.

## Security considerations
- **No biometric data leaves the device**. Only signatures are transmitted.  
- **Attestation** to ensure keys are device-originated.  
- **Per-app policies** stored locally and optionally mirrored on backend for auditing.  
- **Revocation** mechanism to invalidate keys in case of device loss.

## Developer setup (demo)
```bash
git clone https://github.com/blessingowobi25-star/biometric__keychain.git
cd biometric__keychain
# Add demo server and SDK later
---


- **Stage 4A Scope:** Documentation + technical scaffold only.  
⚙️ Production build will include biometric attestation & secure recovery layers.
