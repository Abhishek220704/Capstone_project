
# 🔐 Quantum Cryptography for Secure IoT

A Python-based simulation of a secure encrypted chat system leveraging **Quantum Key Distribution (BB84 Protocol)** and **AES-GCM encryption**, tailored to demonstrate the principles of **Quantum Cryptography** for securing IoT communications.

---

## 🚀 Project Overview

This project simulates a **Quantum Cryptography**-based secure communication system, integrating:

- 🧠 **BB84 Quantum Key Distribution (QKD)** for secure key generation
- 🔒 **AES-GCM (Galois/Counter Mode)** for authenticated encryption
- 📌 **HKDF** (HMAC-based Key Derivation Function) for key expansion
- 📑 **Key Index Obfuscation** to securely hide the correct key
- 🔄 **Alternating Real-Time Chat Simulation** with auto-expiry session
- 🔧 **Logging & Debug Information** for secure audits

The project is designed as a secure encrypted chat system mimicking communication between IoT devices using quantum-derived keys.

---

## 🧪 Key Features

- ✅ **Simulated BB84 QKD**: Sender and Receiver generate bases and reconcile keys based on matching positions.
- ✅ **Index Encryption**: The correct key index is encrypted using AES-GCM and shared with the receiver.
- ✅ **Key Verification**: Only the correct key (selected via decrypted index) can unlock the chat session.
- ❌ **Failsafe Exit**: Incorrect key immediately halts the program and denies access.
- 🔁 **Secure Chat Session**: Continuous messaging until a random threshold is reached, after which the key is destroyed.
- 🧾 **Chat Logging**: All encrypted/decrypted messages are logged to `chat_log.txt`.

---

## 📂 File Structure

```
.
├── quantum_secure_chat.py    # Main Python script
├── chat_log.txt              # Logs of encrypted/decrypted messages
└── README.md                 # Project documentation
```

---

## ⚙️ How It Works

1. **Quantum Key Generation (Simulated)**  
   Sender and Receiver randomly generate bits and bases. Only positions with matching bases are used to generate the final shared key.

2. **Key Expansion via HKDF**  
   The shared key is hashed (SHA-256) and passed through HKDF to derive a secure 128-bit AES key.

3. **Secure Key Verification**  
   - 10 random keys are generated.
   - The correct key is inserted at a random index.
   - The index is encrypted and shared.
   - Receiver decrypts the index, picks the key, and enters it.

4. **Encrypted Chat Session**  
   - Only if the correct key is provided, the chat starts.
   - Messages are encrypted with AES-GCM and decrypted securely.
   - The session expires after a few messages (3–6), simulating key expiry.

---

## 🔐 Technologies Used

- **Python 3.8+**
- `numpy` – For random bit/basis generation
- `pycryptodome` – AES encryption (GCM mode)
- `cryptography` – HKDF for key derivation
- `logging` – Secure chat logging

---

## 🎯 Use Case: Secure IoT Communication

This project demonstrates how **Quantum Cryptography** principles can be adapted to **secure IoT devices**, particularly in:

- 🔸 Sensor-to-server communications
- 🔸 Secure device pairing
- 🔸 Confidential chat between embedded systems
- 🔸 Post-quantum cryptographic exploration

By leveraging QKD and symmetric encryption, this approach offers **quantum-safe communication** that is resistant to both classical and quantum attacks.

---

## 🛠️ Future Extensions

- 🌐 Integration with **MQTT** or **WebSockets** for real-time IoT communication
- 🖥️ GUI Interface for visualization
- 🧪 Add **Post-Quantum Cryptography (PQC)** like **Kyber/Dilithium**
- 🔄 Support for multiple IoT nodes

---

## 📸 Screenshot (Sample Output)

```
🚀 Secure Encrypted Chat Initialized...

🔒 Encrypted Index: yiCHQhzmJGoMyI8zXWsB2rM2suSMbCeX7EIWigoiC8U4
1. ...
2. ...
...
🔢 Decrypted Index: 4
🔑 Enter the correct shared key:
✅ Key Verified! Secure chat established. 🔐
📝 Sender, enter message: Hello!
📤 Encrypted Message: ...
📩 Decrypted Message: Hello!
...
🔐 Secure Key Destroyed. Chat Ended. 🚀
```

---

## 📜 License

This project is for educational and research purposes. Feel free to modify or expand upon it for your use case.
