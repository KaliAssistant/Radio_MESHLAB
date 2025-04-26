# 🔧 Opportunistic Encrypted Mesh Routing Model

## 📖 Overview

This mesh routing model is designed for **secure, lightweight, scalable communication** over RF links (LoRa, FSK, etc.), with a focus on **dynamic discovery**, **per-peer encryption**, and **gradient-based routing** without requiring full routing tables or LSAs.

Inspired by ideas like **Opportunistic Gradient Routing (OGR)** and **distance-vector** methods, this model improves on scalability and privacy for dense wireless mesh networks.

---

## 🧩 Components

### 🔹 Node Identity
- Each node has a **unique NodeID**.
- Upon startup, it generates a **Curve25519 keypair** (if not already provisioned).
- NodeID is not directly exposed in raw packets unless decrypted, adding a **layer 2.5 obfuscation**.

### 🔹 Neighbor Table
- Each node stores a table of **known neighbors**, including:
  - Public key
  - Last seen timestamp
  - Estimated hop distance
  - Link quality (optional)

---

## 📡 Hello Protocol (Neighbor Discovery)

1. A node sends a **non-encrypted "hello" packet** with:
   - Its public key
   - A hop count limit (`TTL`)
   - Optional "key hint" or NodeID hash

2. Neighbors receive and:
   - Respond with their **public key**, establishing a shared key via **Curve25519**.
   - **Forward the hello** to their own neighbors using **encrypted unicast**.
   - Update or ignore the forwarded hello based on TTL and previously recorded hop distance.

3. Result: nodes learn about their **direct and remote neighbors** without flooding the network.

---

## 🔐 Encryption Model

- All unicast communications are **AES-encrypted** using a shared key derived from Curve25519 exchange.
- Broadcast packets (like hello) are plaintext or partially encrypted (hybrid).
- The design **avoids revealing NodeID or source unless decryption succeeds**.

---

## 🚚 Packet Routing

- Forwarding uses a **gradient**: nodes prefer lower-hop paths (shorter TTL seen).
- No global route calculation.
- Intermediate nodes **forward encrypted packets** if:
  - They can decrypt it (key match)
  - The destination is in their neighbor/remote table

---

## 🔄 Topology Adaptation

- If a node sees the same originator with a **lower TTL (shorter path)** than before, it updates the route.
- If the TTL is worse (longer path), the packet is dropped.
- Neighbor/remote records expire if not refreshed, simulating node loss or movement.

---

## 💡 Advantages

- ⚡ **Lightweight**: No LSAs or full routing table floods
- 🔐 **Secure**: Curve25519 + AES with source obfuscation
- 🌱 **Scalable**: Works in large networks (1k+ nodes)
- 🧠 **Self-healing**: Opportunistic update mechanism

---

## 🧪 Ideal Use Cases

- LoRa / low-power radio networks
- Mesh sensor swarms or drones
- Environments with **high churn** and **unreliable links**

---

## 🛠 Next Steps

- Implement in Python/MCU/C++ with RadioLib support
- Add visual simulator with GUI (e.g., Tkinter)
- Optimize neighbor selection and gradient updates

