# GetX for Web3 (Flutter)

**GetX** is a lightweight and powerful state management solution for Flutter. It's ideal for managing wallet connections, contract state, and async Web3 data streams in Web3 Flutter applications.

---

## 🚀 Why Use GetX in Web3 Apps?

- 🔄 Reactive UI for real-time blockchain updates
- 🚀 Easy to manage state for connected accounts, balances, etc.
- 🧪 Clean separation of UI and logic (GetBuilder, Obx)

---

## 🧱 Setup

### ✅ Install Packages

```yaml
dependencies:
  get: ^4.6.6
  web3dart: ^2.6.1
  http: ^0.13.4
```

---

## 🧠 Folder Structure (Example)

```
/controllers
  └── wallet_controller.dart
/views
  └── home_view.dart
/main.dart
```

---

## 🎮 Example: WalletController

```dart
class WalletController extends GetxController {
  final address = "".obs;
  final balance = Rx<BigInt>(BigInt.zero);

  late Web3Client client;

  @override
  void onInit() {
    super.onInit();
    client = Web3Client("https://sepolia.infura.io/v3/YOUR_KEY", http.Client());
    connectWallet();
  }

  Future<void> connectWallet() async {
    final credentials = EthPrivateKey.fromHex("YOUR_PRIVATE_KEY");
    final addr = await credentials.extractAddress();
    address.value = addr.hex;
    balance.value = await client.getBalance(addr);
  }
}
```

---

## 🖥 View: Reactive UI with Obx

```dart
class HomeView extends StatelessWidget {
  final controller = Get.put(WalletController());

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Center(
        child: Obx(() => Column(
          children: [
            Text("Address: ${controller.address}"),
            Text("Balance: ${controller.balance.value} wei"),
          ],
        )),
      ),
    );
  }
}
```

---

## 🔐 Handling Sensitive Data

- Store private keys using `flutter_secure_storage`
- Do **not** hardcode sensitive values in source code
- Use `.env` or encrypted storage if necessary

---

## 📚 Resources

- [GetX Docs](https://pub.dev/packages/get)
- [web3dart](https://pub.dev/packages/web3dart)
- [Flutter Secure Storage](https://pub.dev/packages/flutter_secure_storage)

---

✍️ Created by [@alkhatib99](https://github.com/alkhatib99)
