# Edwiser Bridge (Free): Code Understanding Map

This document provides a function-level understanding of the Edwiser Bridge (Free) plugin, focusing on critical functions and files most relevant to client issues and debugging.

---

## 1. Main Plugin Bootstrap
- **File:** `edwiser-bridge.php`
- **Purpose:** Initializes the plugin, loads modules, sets up hooks and activation/deactivation routines.
- **Critical Functions:**
  - `edwiser_bridge_activate()` / `edwiser_bridge_deactivate()`
    - Handles setup and cleanup on plugin activation/deactivation.
    - **Edge Cases:** Database/table creation failures, permission issues.

## 2. Setup Wizard
- **Files:** `admin/setup-wizard/`
- **Key Classes/Functions:**
  - `class-eb-setup-wizard-functions.php` — Core logic for setup steps and Moodle connection.
  - `class-eb-setup-wizard-templates.php` — UI templates for the wizard.
- **Common Issues:** API credential errors, incomplete setup, connection failures.

## 3. Course & User Sync
- **Files:** `admin/settings/`, `includes/`
- **Key Classes/Functions:**
  - `class-eb-settings-synchronization.php` — Handles scheduled/manual sync of courses and users.
  - `class-eb-settings-connection.php` — Manages Moodle connection settings.
  - `class-eb-admin.php` — Core admin logic, including sync triggers.
- **Common Issues:** Sync failures, API errors, user/course mapping issues.

## 4. Licensing & Updates
- **Files:** `freemius/`, `admin/licensing/`
- **Key Classes/Functions:**
  - `class-eb-licensing-manager.php` — Handles license validation and management.
  - `class-fs-plugin-updater.php` — Manages plugin updates via Freemius.
- **Common Issues:** License activation errors, update failures, Freemius API issues.

## 5. Admin Settings & Error Logging
- **Files:** `admin/settings/`, `admin/`
- **Key Classes/Functions:**
  - `class-eb-settings-page.php` — Renders and processes admin settings pages.
  - `class-eb-error-log.php` — Manages error log display and storage.
- **Common Issues:** Settings not saving, error log not updating, permission issues.

## 6. Shortcodes & Widgets
- **Files:** `admin/settings/class-eb-settings-shortcode-doc.php`, `admin/partials/`
- **Key Classes/Functions:**
  - Shortcode registration and documentation for course display/enrollment.
- **Common Issues:** Shortcode rendering errors, attribute parsing problems.

---

## Debugging Tips
- **Sync Issues:** Check Moodle API credentials, endpoint URLs, and user/course mapping.
- **Setup Wizard Problems:** Ensure all required fields are filled and Moodle is accessible.
- **Licensing/Update Issues:** Verify Freemius connection and license status.
- **Settings/Log Issues:** Check file permissions and server error logs.

This map is a quick reference for support and debugging. For detailed code, refer to the specific file and class/function listed above. 