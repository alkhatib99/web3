# Environment Variables & Security in Web3 Development

Managing API keys, private keys, and sensitive config in Web3 development requires caution. This guide covers how to store, load, and protect these secrets properly.

---

## 🔐 Why Use Environment Variables?

- Keeps sensitive data out of your source code
- Easier to manage across different environments (dev/test/prod)
- Prevents accidental exposure of private keys or API keys

---

## 📁 Common Secrets to Protect

- Ethereum private keys
- Infura / Alchemy RPC API keys
- Pinata / IPFS JWT tokens
- Etherscan API keys
- Smart contract admin credentials

---

## 🧱 `.env` Setup (Node.js / Hardhat)

### 1. Install dotenv

```bash
npm install dotenv
```

### 2. Create `.env`

```env
PRIVATE_KEY=0x123abc...
INFURA_API_KEY=abc123xyz
```

### 3. Load `.env` in `hardhat.config.js`

```js
require("dotenv").config();

module.exports = {
  networks: {
    sepolia: {
      url: `https://sepolia.infura.io/v3/${process.env.INFURA_API_KEY}`,
      accounts: [process.env.PRIVATE_KEY]
    }
  }
};
```

---

## 🛡 Flutter: Use flutter_dotenv

```yaml
dependencies:
  flutter_dotenv: ^5.0.2
```

### Load `.env` in `main.dart`

```dart
import 'package:flutter_dotenv/flutter_dotenv.dart';

Future main() async {
  await dotenv.load();
  runApp(MyApp());
}
```

Access variables:

```dart
dotenv.env['INFURA_KEY']
```

---

## ⚠️ Best Practices

- Always add `.env` to `.gitignore`
- Use `flutter_secure_storage` for storing keys on mobile
- NEVER commit private keys to GitHub
- Rotate your secrets regularly

---

## 📚 Resources

- [dotenv (Node.js)](https://www.npmjs.com/package/dotenv)
- [flutter_dotenv](https://pub.dev/packages/flutter_dotenv)
- [flutter_secure_storage](https://pub.dev/packages/flutter_secure_storage)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
