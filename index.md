---
layout: default
title: InKeyAll Documentation
---

# 🗝️ InKeyAll
### The Ultimate KeyAll Plugin 

**InKeyAll** is a professional-grade Minecraft plugin designed to drive player engagement through automated "KeyAll" events and community-driven player-count milestones.

📥 [Download Latest Version](https://modrinth.com/project/inkeyall) | [📄 View Default Config](config.yml)

---
## 🚀 Features
* **Timed KeyAlls:** Create unlimited repeating rewards with unique intervals.
* **Community Goals:** Automatically reward players when server milestones are reached.
* **Smart Logic:** Built-in cooldowns and reload-handling to prevent reward abuse.
* **Dual Placeholder System:** Supports both internal config-based logic and external PAPI integration.

---

## 📊 Placeholders: Internal vs. External

### **1. Internal Placeholders (Plugin Only)**
**⚠️ Important:** These placeholders **CANNOT** be used in other plugins (like Scoreboards or Tab). They are strictly for use inside the `config.yml` of InKeyAll.

| Placeholder | Where to use | Description |
| :--- | :--- | :--- |
| `%online%` | `goals-message` | Current online player count. |
| `%required%` | `goal-line-format` | Players needed for that specific milestone. |
| `%milestone_id%` | `goal-line-format` | The ID name of the milestone. |
| `%goals_list%` | `goals-message` | Injects the full list of active milestones. |
| `%player_name%` | `key-command` | The name of the player receiving the command. |
| `%key_name%` | `broadcast-message` | The display name of the key/reward. |

### **2. External Placeholders (Universal/PAPI)**
**✅ Usage:** These **CAN** be used anywhere (Scoreboards, Tab, Chat, Holograms) as long as you have PlaceholderAPI installed. They all require the `inkeyall` prefix.

| Placeholder | Description |
| :--- | :--- |
| `%inkeyall_player_name%` | Returns the player's name. |
| `%inkeyall_server_online%` | Returns current server online count. |
| `%inkeyall_milestone_goal_<id>%` | Target player count for a specific milestone. |
| `%inkeyall_timer_<id>%` | Standard short timer (Configurable) |
| `%inkeyall_timer_full_<id>%` | Full format timer (Configurable) |
| `%inkeyall_timer_optimised_<id>%` | Smart-hides zero units (Short) |
| `%inkeyall_timer_optimised_full_<id>%` | Smart-hides zero units (Full) |

---

## 🎮 Commands & Permissions

| Command | Alias | Description | Permission |
| :--- | :--- | :--- | :--- |
| `/goals` | `/milestones` | View community goal progress | `inkeyall.goals` |
| `/inkeyall reload` | `/ka reload` | Reload config and restart tasks | `inkeyall.reload` |
| `/inkeyall <id>` | `/ka <id>` | Manually trigger a specific KeyAll | `inkeyall.use` |

---

## ⚙️ Configuration Example

```yaml
milestone-settings:
  enabled: true
  goals-message:
    - "&b&l--- Community Goals ---"
    - "&7Currently: &f%online% &7players" # Internal Use Only
    - ""
    - "%goals_list%" # Internal Use Only
    - ""
    - "&b&l-----------------------"
```
---

## 🛠️ Installation

1. Download `InKeyAll.jar` from the [Releases](https://modrinth.com/project/inkeyall) tab.
2. Place the JAR into your server's `/plugins/` folder.
3. Restart your server.
4. (Optional) Install **PlaceholderAPI** to use the external placeholders in your Scoreboard.
5. Customize your `config.yml` and run `/inkeyall reload`.

---

© 2025 InnocentDevYT. Built for the Minecraft Community.
