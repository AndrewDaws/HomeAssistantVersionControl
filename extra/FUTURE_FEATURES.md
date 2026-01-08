# Home Assistant Version Control - Future Features

## Reload Hack

**Description:** Auto-reload Home Assistant components when their config files change - even without using version control features.

**How it works:**
- File watcher detects change to config file
- Add-on calls HA REST API to reload that component
- User doesn't need to manually reload in HA UI

**File → Reload API mapping:**
| File | API Endpoint |
|---|---|
| `automations.yaml` | `automation.reload` |
| `scripts.yaml` | `script.reload` |
| `scenes.yaml` | `scene.reload` |
| `groups.yaml` | `group.reload` |
| `input_boolean.yaml` | `input_boolean.reload` |
| `input_number.yaml` | `input_number.reload` |
| `input_select.yaml` | `input_select.reload` |
| `input_text.yaml` | `input_text.reload` |
| `input_datetime.yaml` | `input_datetime.reload` |
| `timer.yaml` | `timer.reload` |
| `counter.yaml` | `counter.reload` |
| `switches.yaml` | `template.reload` |
| `sensors.yaml` | `template.reload` |
| `binary_sensors.yaml` | `template.reload` |
| `lights.yaml` | `template.reload` + `group.reload` |
| `command_line.yaml` | `command_line.reload` |
| `homekit.yaml` | `homekit.reload` |
| `customize.yaml` | `homeassistant.reload_core_config` |

**Notes:**
- Some files may need multiple reloads (template + mqtt, etc.)
- Optional toggle to enable/disable auto-reload
- Useful standalone feature even without version control

---

## Hard Reset via Context Menu (DANGER DOES DELETE FILES WHEN HARD RESET - MAYBE WE DO SOFT RESET?)

**Description:** Ability to right-click any commit in the timeline history to "Hard Reset" to that state.

**Functionality:**
- **Action:** Right-click context menu on timeline item -> "Reset to this state"
- **Effect:** 
  - Restores all files to that exact version
  - **Destructive:** Permanently removes all commits AFTER that point
  - Effectively rewinds time for the repository
- **Safety:** Should require a confirmation dialog ("Are you sure? This will delete X subsequent versions.")

---

## Dual Cloud Push (GitHub + Custom)

**Description:** Ability to push to both GitHub and a Custom remote simultaneously.

**UI Logic:**
- If **BOTH** GitHub and Custom providers are successfully connected:
  - A new toggle/option appears in the Cloud Provider selector: **"Both"** (or "All Connected").
- **Functionality:**
  - When "Both" is selected, the push action loops through and pushes to `origin` (GitHub) AND the custom remote.
  - Useful for redundancy (e.g., Public GitHub backup + Private local Gitea backup).
