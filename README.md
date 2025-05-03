# !!!!Fork from the original, not really a proactive maintenance just try to unlock my Domoticz and publish result in this repo .


# Domoticz-Unifi-Presence

## 🛰️ UniFi Presence Detection Plugin for Domoticz

This Domoticz plugin allows presence detection using a UniFi Controller, Dream Machine Pro, or CloudKey Gen2.  
It tracks devices (e.g., smartphones) connected to your network and can trigger actions in Domoticz based on their presence.

---

## ✅ Features

- Detects presence based on MAC address association.
- Supports UniFi Controller and Dream Machine Pro (via appropriate login endpoints).
- Supports geofencing via virtual devices.
- **NEW (v4.0.1):**
  - Automatic re-login when UniFi session expires (`HTTP 401`).
  - Prevents device reinitialization on re-login (no more unwanted ON/OFF switches).
  - Code cleaned up for better maintainability and readability (docstrings added).

---

## 🧰 Requirements

- Domoticz with Python plugin support
- Python 3.6+
- `requests` module
- Access to UniFi Controller or Dream Machine/CloudKey Gen2

---

## 🚀 Installation

1. Clone this repository into the `plugins` directory of Domoticz:
    ```bash
    git clone https://github.com/lacha07/Domoticz-Unifi-Presence.git
    ```

2. Restart Domoticz:
    ```bash
    sudo systemctl restart domoticz
    ```

3. In the Domoticz interface, go to **Hardware** and add a new device:
    - Type: *Unifi Presence Detection*
    - IP Address: Your controller IP
    - Port: `8443` (or custom if changed)
    - Username / Password: your UniFi credentials
    - Site: `default` or as configured
    - Device list: comma-separated MAC addresses and names

---

## 🔄 Upgrade Notes (v4.0.1)

- 🛡️ Plugin now handles **expired sessions automatically** and retries login without impacting Domoticz behavior.
- 🧠 Added logic to **only initialize devices on first login**, preventing "flickering" of presence switches.
- ⚙️ Improved reliability for long-running systems.

---

## 📦 Versions

| Version | Notes |
|---------|-------|
| 1.0.0 - 3.0.8 | Original versions by Wizzard72 |
| 4.0.0 | Changed startup sequence |
| **4.0.1** | ✅ Added 401 retry, device init guard, improved comments and docstrings |

---

## 📞 Example MAC List

```
Phone1=1A:2B:3C:4D:5E:6F,Phone2=7A:8B:9C:AD:BE:CF
```

---

## 🤝 Acknowledgements

- Original author: **Wizzard72**
- Maintenance and improvements: **lacha07**
- Thanks to the Domoticz community for support and feedback

---

## 📜 License

MIT License

