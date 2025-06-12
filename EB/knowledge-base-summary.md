# Edwiser Bridge Pro: Knowledge Base Summary

## Overall Functionality & Purpose
Edwiser Bridge Pro is a WordPress plugin that provides deep integration between WordPress and Moodle, enabling seamless e-learning commerce, user management, and course synchronization. It extends the core Edwiser Bridge plugin with advanced features for bulk purchase, selective sync, custom fields, single sign-on (SSO), WooCommerce integration, and more.

## Architecture & Integration
- **WordPress Integration:** The plugin is installed and managed as a standard WordPress plugin, leveraging hooks, shortcodes, widgets, and the WordPress admin interface.
- **Moodle Integration:** Communicates with Moodle via web services and APIs to sync courses, users, and enrollments. SSO modules allow users to log in to both platforms with a single account.
- **WooCommerce Integration:** Deep integration with WooCommerce for course sales, order management, and product synchronization.
- **Modular Structure:** Organized into modules for bulk purchase, custom fields, selective sync, SSO, WooCommerce integration, and more. Each module is further divided into admin, includes, public, and assets.

## Key Modules & Features
- **Bulk Purchase:** Group enrollments, CSV upload, cohort management, group email templates, and admin notices for bulk actions.
- **Custom Fields:** Add, sync, and validate custom user/course fields between WordPress and Moodle.
- **Selective Sync:** Sync only selected courses or users between platforms, with AJAX handlers and admin UI.
- **Single Sign-On (SSO):** Social login (Facebook, Google, LinkedIn), SSO session management, and redirection.
- **WooCommerce Integration:** Product API, order manager, product manager, membership handler, AJAX endpoints, and compatibility with WooCommerce account pages.
- **Shortcodes & Widgets:** Custom shortcodes for course enrollment, checkout, and user management; widgets for product and related course display.
- **Admin & Public Assets:** Custom CSS/JS for admin and public interfaces, including DataTables, Select2, and UI enhancements.

## Dependencies & Configuration
- **Dependencies:**
  - WordPress (latest recommended)
  - Moodle (for integration)
  - WooCommerce (for e-commerce features)
  - Social login libraries (Facebook, Google, LinkedIn SDKs)
  - DataTables, Select2, jQuery (bundled in assets)
- **Configuration Steps:**
  - Set up Moodle web services and connect via plugin settings
  - Configure WooCommerce products and link to Moodle courses
  - Enable and configure SSO providers as needed
  - Set up custom fields and selective sync options in the admin panel
  - Review and adjust email templates, admin notices, and bulk purchase settings

## Notable Files
- `edwiser-bridge-pro.php`: Main plugin bootstrap file
- `admin/`, `includes/`, `public/`: Contain module logic, assets, and UI
- `readme.txt`: Documentation and changelog

---
This summary provides a high-level reference for support, onboarding, and debugging. See the code understanding map for function-level details. 