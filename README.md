# Radio_MESHLAB

Main project repository of Radio Mesh AREA Network

## 1. Why I created this repository:

I aim to build a mesh communication network standard applicable to **any digital radio frequency module**, following a top-down OSI layered approach:

- Custom user-defined **Application** and **Session** layers  
- Establishment of a **stable and reliable transport protocol**  
- **Smart & automated** routing and node discovery  
- Layer 2 encapsulation using **nearly immutable hardware unique IDs** and **secure encryption standards**  
- **Cross-platform, embedded system support** with wide hardware compatibility  

## 2. Difference from Meshtastic:

Meshtastic is an outstanding project, and I’ve used it for some time. However, I noticed that most mesh networks are limited to *local area meshes*, relying on backbone links for further expansion.

While I cannot break through the fundamental limitations of mesh distance, this project attempts to **optimize transmission distance through support for multiple RF modules**.

Additionally, I hope to enable **custom application layers**, moving beyond Meshtastic’s text/audio use cases — making **file transfer possible**, similar to FTP. Note: application layer development is outside the scope of this project and is **entirely up to users** to define.

---

## 3. Repositories of this project

- Layer 4: Radio_TCP -->  [Radio_TCP](https://github.com/KaliAssistant/Radio_TCP.git)
- Layer 2.5: Radio_Mesh_Routing --> [Radio_Mesh_Routing](https://github.com/KaliAssistant/Radio_Mesh_Routing.git)
- iptables-like FireWall : Radio_RF_TABLES --> [Radio_RF_TABLES](https://github.com/KaliAssistant/Radio_RF_TABLES.git)

⚠️ **This repository will be updated very slowly.**  
I can multitask, but life and other projects may take precedence.

👥 Interested contributors are **welcome to open issues or PRs!**
