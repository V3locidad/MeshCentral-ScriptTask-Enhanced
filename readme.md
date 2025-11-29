# MeshCentral ScriptTask Enhanced

Enhanced version of the original **ScriptTask plugin** for MeshCentral, including **multi-endpoint execution**, **Dry Run (simulation) mode**, and **UI improvements**.

[![Version](https://img.shields.io/badge/version-0.1.0-blue.svg)](https://github.com/V3locidad/MeshCentral-ScriptTask-Enhanced)  
[![Maintainer](https://img.shields.io/badge/maintainer-V3locidad-orange)](https://github.com/V3locidad)

---

## 📌 Table of Contents

- [Features](#features)
- [Installation](#installation)
  - [Automatic](#automatic-recommended)
  - [Manual](#manual)
- [Usage](#usage)
- [Dry Run Example](#dry-run-example)
- [Plugin Structure](#plugin-structure)
- [Requirements](#requirements)
- [Changelog](#changelog)
- [Author](#author)
- [License](#license)
- [Future Improvements](#future-improvements)
- [Credits](#credits)

---

## 🚀 Features

- Run scripts on **multiple endpoints** at once  
- **Dry Run (simulation mode)** to preview targeted nodes before execution  
- Improved **UI logic**: the main **Run** button now respects selected endpoints  
- Compatible with **MeshCentral ≥ 1.1.35** (tested on **v1.1.53**)  
- Fixes the original multi-endpoint execution behavior  

---

## 🔧 Installation

### ⚠️ Important: Replacing the Original ScriptTask Plugin

If you already have the original ScriptTask plugin installed, you **must** uninstall it first to avoid conflicts:

1. Log into MeshCentral as administrator
2. Go to **My Server** (top right)
3. Click on the **Plugins** tab
4. Find the original "ScriptTask" plugin
5. Click the **Disable** next to the plugin
6. Select **Delete**
7. Confirm the deletion

### ⚙️ Automatic Installation (Recommended)

1. Go to **My Account** → **Plugins**
2. Click **Download Plugin**
3. Paste the config URL: `https://raw.githubusercontent.com/V3locidad/MeshCentral-ScriptTask-Enhanced/main/config.json`

### 📝 Configuration

Ensure plugins are enabled in your MeshCentral `config.json`:
```json
"plugins": {
  "enabled": true
}
```

### 🔄 Restart MeshCentral

After installation, **restart MeshCentral** to clear the cache and load the plugin:
```bash
# If using systemd
systemctl restart meshcentral

# Or if running manually
# Stop MeshCentral (Ctrl+C) and start it again
node node_modules/meshcentral
```

### 🌐 Clear Browser Cache

After restarting MeshCentral, **clear your browser cache** or use **Ctrl + F5** (Cmd + Shift + R on Mac) to force reload the page.

### ✅ Verify Installation

1. Log into MeshCentral as a full administrator
2. Navigate to a device/endpoint
3. Look for "ScriptTask Enhanced" in the available plugins/actions

---

## 🖥️ Usage

1. Log into MeshCentral as a full administrator
2. Open the ScriptTask plugin
3. Select a script from the tree
4. Select one or multiple endpoints using the checkboxes
5. Click:
   - **Run** → execute on selected nodes (or current node if none selected)
   - **Dry Run (Simulation)** → preview execution without running

---

## 🔍 Dry Run Example
```
DRY RUN SIMULATION
Script: DeployUpdate.ps1
Target machines: 3

Endpoints:
 - SERVER-01
 - PC-TEST-02
 - LAPTOP-03

No action has been executed.
```

ℹ️ Dry Run is fully read-only — nothing is executed on endpoints.

---

## 📁 Plugin Structure
```
scripttask/
├── scripttask.js          # Core plugin logic
├── views/                 # UI templates (Handlebars / HTML)
├── modules_meshcore/      # MeshCore integration
├── includes/              # Extra JS/CSS assets
├── config.json            # Plugin configuration descriptor
├── changelog.md
└── LICENSE
```

---

## 📎 Requirements

| Requirement | Minimum |
|-------------|---------|
| MeshCentral | 1.1.35 |
| Node.js | Compatible with your MeshCentral version |
| Plugin system enabled | Yes |

---

## 📜 Changelog

### v0.1.0 – Initial Enhanced Release

- Fixed multi-endpoint execution behavior
- Added Dry Run (simulation) mode
- Updated Run button logic to honor selected endpoints
- Maintains full compatibility with original ScriptTask database format

---

## 👤 Author

**Julien (V3locidad)**

🛠️ BugHunter / MeshCentral plugin developer  
🔗 GitHub: https://github.com/V3locidad

---

## 📄 License

This project is released under the **MIT License**.  
See the `LICENSE` file for details.

---

## 🔮 Future Improvements

Planned / possible upgrades:

- Live progress tracking (ex: *Running (2/10) endpoints…*)
- Confirmation prompt when executing on large number of devices
- "Run now" option directly from the Dry Run popup
- Support for script parameters / inputs
- Webhooks / Teams / Discord notifications on completion

---

## 🙏 Credits

- **Original ScriptTask plugin**: Ryan Blenis
- **Enhancements & fixes**: V3locidad
