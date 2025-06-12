# Edwiser Bridge Pro: Code Understanding Map

This document provides a function-level understanding of the Edwiser Bridge Pro plugin, focusing on critical functions and files most relevant to client issues and debugging.

---

## 1. Main Plugin Bootstrap
- **File:** `edwiser-bridge-pro.php`
- **Purpose:** Initializes the plugin, loads modules, sets up hooks and activation/deactivation routines.
- **Critical Functions:**
  - `edwiser_bridge_pro_activate()` / `edwiser_bridge_pro_deactivate()`
    - Handles setup and cleanup on plugin activation/deactivation.
    - **Edge Cases:** Database/table creation failures, permission issues.

## 2. Bulk Purchase Module
- **Files:** `includes/bulk-purchase/`
- **Key Classes/Functions:**
  - `class-eb-bp-admin-notices.php` — Displays admin notices for bulk actions.
  - `class-eb-bp-ajax-handler.php` — Handles AJAX requests for group management, enrollments, CSV uploads.
  - `class-eb-bp-enrollment-manager.php` — Manages group enrollments and cohort assignments.
  - `eb-bp-functions.php` — Utility functions for bulk purchase logic.
  - `eb-bp-upload-csv.php` — Handles CSV upload and parsing for bulk enrollments.
- **Common Issues:** CSV format errors, AJAX failures, enrollment sync problems.

## 3. Custom Fields Module
- **Files:** `includes/custom-fields/`
- **Key Classes/Functions:**
  - `class-eb-pro-custom-fields.php` — Registers and manages custom fields.
  - `class-edwiser-custom-field-handler.php` — Handles field data processing and validation.
  - `class-edwiser-custom-field-sync-handler.php` — Syncs custom fields between WordPress and Moodle.
- **Common Issues:** Field validation errors, sync mismatches, missing fields.

## 4. Selective Sync Module
- **Files:** `includes/selective-sync/`
- **Key Classes/Functions:**
  - `class-eb-pro-selective-sync.php` — Core logic for selective course/user sync.
  - `class-eb-select-course-ajax-handler.php` — AJAX handler for course selection.
  - `class-eb-select-users-ajax-handler.php` — AJAX handler for user selection.
- **Common Issues:** Incomplete sync, AJAX timeouts, permission errors.

## 5. SSO (Single Sign-On) Module
- **Files:** `includes/sso/`, `admin/settings/`
- **Key Classes/Functions:**
  - `class-eb-pro-sso.php`, `class-single-sign-on.php` — SSO session and login management.
  - `class-sso-settings-*.php` — SSO configuration and provider settings.
  - Social login handlers (Facebook, Google, LinkedIn): `class-sso-facebook-init.php`, `class-sso-gp-user-manager.php`, etc.
- **Common Issues:** SSO login failures, provider misconfiguration, session persistence issues.

## 6. WooCommerce Integration
- **Files:** `includes/woo-int/`, `admin/settings/class-bridge-woocommerce-settings.php`
- **Key Classes/Functions:**
  - `class-bridge-woocommerce-ajax.php` — Handles WooCommerce-related AJAX actions.
  - `class-bridge-woocommerce-order-manager.php` — Manages order sync and status updates.
  - `class-bridge-woocommerce-product-manager.php` — Handles product sync and mapping.
  - `class-bridge-woo-membership-handler.php` — Membership and access control logic.
- **Common Issues:** Order sync failures, product mapping errors, AJAX issues.

## 7. Shortcodes & Widgets
- **Files:** `public/shortcodes/`, `public/widgets/`
- **Key Classes/Functions:**
  - `class-eb-shortcode-enroll-users.php` — Shortcode for user enrollment.
  - `class-bridge-woocommerce-shortcode-associated-courses.php` — Shortcode for displaying associated courses.
  - `class-eb-pro-product-page-widget.php` — Widget for product display.
- **Common Issues:** Shortcode rendering errors, widget display issues, attribute parsing problems.

## 8. General Utilities & Activation
- **Files:** `includes/class-eb-pro-activator.php`, `includes/class-eb-pro-deactivator.php`, `includes/class-eb-pro-plugin-updater.php`
- **Purpose:** Handles plugin activation, deactivation, and update routines.
- **Common Issues:** Update failures, database migration issues, cleanup problems.

---

## Debugging Tips
- **AJAX Issues:** Check browser console and server logs for errors. Ensure correct nonce and permissions.
- **Sync Problems:** Verify Moodle connection, API credentials, and user/course mapping.
- **Enrollment/Order Issues:** Check WooCommerce order status, user roles, and group assignments.
- **SSO Failures:** Review provider configuration, callback URLs, and session settings.

This map is a quick reference for support and debugging. For detailed code, refer to the specific file and class/function listed above. 