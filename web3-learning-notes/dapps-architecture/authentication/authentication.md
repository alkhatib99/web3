# Authentication in Web3

In Web3, authentication is typically handled using cryptographic signatures rather than traditional usernames and passwords. Users "sign in" by proving ownership of their wallet address.

---

## 🔐 Sign-In With Ethereum (SIWE)

**SIWE** is a standardized way for users to authenticate using their wallet.  
It involves signing a structured message that a backend can verify.

### 🧱 How It Works

1. The frontend generates a SIWE message.
2. The user signs it using their wallet (e.g., MetaMask).
3. The signature is sent to the backend.
4. Backend verifies signature and issues a session/token.

---

## ✍️ Example Message (EIP-4361)

```
service.org wants you to sign in with your Ethereum account:
0xAbc...

URI: https://service.org/login
Version: 1
Chain ID: 1
Nonce: 32891757
Issued At: 2025-05-10T12:00:00Z
```

---

## 📦 Using SIWE (with NextAuth + ethers.js)

```js
import { SiweMessage } from 'siwe';

async function signInWithEthereum() {
  const signer = await provider.getSigner();
  const message = new SiweMessage({
    domain: window.location.host,
    address: await signer.getAddress(),
    statement: "Sign in to the app",
    uri: window.location.origin,
    version: "1",
    chainId: 1,
    nonce: generateNonce(),
  });
  const signature = await signer.signMessage(message.prepareMessage());
}
```

---

## 🔧 Flutter Approach (Concept)

- Generate a message server-side (or in-app)
- Use `signMessage` from `web3dart`
- Send signature to backend for verification

```dart
final signature = await credentials.signPersonalMessage(Uint8List.fromList(utf8.encode(message)));
```

---

## ✅ Benefits of Wallet-Based Auth

- No password storage
- Truly user-owned identity
- Gasless (no transaction needed)
- Easy integration with existing wallets

---

## ⚠️ Security Notes

- Use HTTPS to avoid MITM attacks
- Bind message to domain and timestamp
- Prevent replay attacks with nonces

---

## 📚 Resources

- [SIWE Docs](https://login.xyz/)
- [EIP-4361](https://eips.ethereum.org/EIPS/eip-4361)
- [NextAuth.js Web3](https://next-auth.js.org/)
- [web3dart (Flutter)](https://pub.dev/packages/web3dart)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
