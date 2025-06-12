# Edwiser Bridge (Free): Knowledge Base Summary

## Overall Functionality & Purpose
Edwiser Bridge (Free) is a WordPress plugin that enables integration between WordPress and Moodle, allowing site owners to synchronize courses, users, and enrollments between the two platforms. It provides a foundation for e-learning commerce and user management, with upgrade paths to the Pro version for advanced features.

## Architecture & Integration
- **WordPress Integration:** Installed as a standard WordPress plugin, using hooks, shortcodes, widgets, and the admin interface for configuration and management.
- **Moodle Integration:** Connects to Moodle via web services and APIs to sync courses, users, and enrollments. Provides setup wizards and admin tools for linking the two systems.
- **Modular Structure:** Organized into admin, includes, setup-wizard, licensing, and assets. Each module handles a specific aspect of the integration or user experience.

## Key Modules & Features
- **Setup Wizard:** Guides administrators through initial configuration and Moodle connection.
- **Course & User Sync:** Synchronizes Moodle courses and users with WordPress, including manual and scheduled sync options.
- **Licensing & Updates:** Manages plugin licensing, updates, and feature unlocks (via Freemius integration).
- **Admin Settings:** Centralized settings for connection, general options, PayPal, synchronization, and shortcodes.
- **Shortcodes & Widgets:** Provides shortcodes for course display and enrollment; widgets for course and user information.
- **Email Templates:** Customizable email templates for notifications and user actions.
- **Error Logging:** Admin tools for viewing and managing error logs.

## Dependencies & Configuration
- **Dependencies:**
  - WordPress (latest recommended)
  - Moodle (for integration)
  - Freemius (for licensing and updates)
  - jQuery, Select2, DataTables (bundled in assets)
- **Configuration Steps:**
  - Set up Moodle web services and connect via plugin settings or setup wizard
  - Configure general, PayPal, and synchronization settings in the admin panel
  - Set up email templates and shortcodes as needed
  - Review licensing and update options

## Notable Files
- `edwiser-bridge.php`: Main plugin bootstrap file
- `admin/`, `includes/`, `setup-wizard/`: Contain module logic, assets, and UI
- `freemius/`: Licensing and update management

---
This summary provides a high-level reference for support, onboarding, and debugging. See the code understanding map for function-level details. 