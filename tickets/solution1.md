# Solution 1: Troubleshooting User Not Enrolled After Product Purchase

This guide helps support staff resolve the issue where a user is not enrolled in a Moodle course after purchasing a WooCommerce product via Edwiser Bridge (Free or Pro).

---

## Step-by-Step Troubleshooting

### 1. Check WooCommerce Order Status
- Enrollment is triggered only when the order status is **"Completed"**.
- Go to WooCommerce > Orders. Complete the order if it is not already completed.

### 2. Verify Product–Course Mapping
- Edit the WooCommerce product. Ensure the "Moodle Course" field is set to the correct course.

### 3. Check Edwiser Bridge & WooCommerce Integration
- Relevant files:
  - Pro: `includes/woo-int/class-bridge-woocommerce-order-manager.php`, `class-bridge-woocommerce-product-manager.php`, `class-bridge-woocommerce-ajax.php`
  - Free: AJAX handlers and product meta fields
- Check for errors in `wp-content/debug.log` and browser console during checkout.

### 4. User Account Issues
- Ensure the user account is created and email is valid.
- If guest checkout is enabled, verify user creation is working.

### 5. Moodle Connection & API
- Go to Edwiser Bridge > Settings > Connection. Test the connection to Moodle.
- Check for API errors or authentication issues.

### 6. Check for Plugin Conflicts
- Temporarily disable other plugins except Edwiser Bridge, WooCommerce, and required dependencies. Test again.

### 7. Review Error Logs
- Check Edwiser Bridge error logs (Admin > Edwiser Bridge > Error Log).
- Check server error logs for PHP or database errors.

### 8. Common Edge Cases
- Order not completed: Enrollment won't trigger.
- Course not mapped: No enrollment will occur.
- API token expired: Moodle won't accept enrollment requests.
- User already enrolled: No duplicate enrollment.
- Bulk/group purchase: Check group assignment logic.

### 9. Manual Enrollment Test
- Try enrolling the user manually via Edwiser Bridge admin. If this fails, the issue is likely with the Moodle connection or user mapping.

### 10. Update Plugins
- Ensure you are using the latest versions of Edwiser Bridge, WooCommerce, and Moodle.

### 11. Contact Support
- If unresolved, provide:
  - Steps to reproduce
  - Error logs
  - Plugin versions
  - Any custom code or overrides

---

## Summary Table: Where to Look in the Code

| Area                        | File(s) to Check (Pro)                                   | File(s) to Check (Free)                |
|-----------------------------|---------------------------------------------------------|----------------------------------------|
| Order → Enrollment Logic    | `class-bridge-woocommerce-order-manager.php`             | (Pro only, but check AJAX handlers)    |
| Product–Course Mapping      | `class-bridge-woocommerce-product-manager.php`           | Product meta fields in admin           |
| Enrollment Trigger          | WooCommerce order hooks, AJAX handlers                   | WooCommerce hooks in main plugin       |
| Moodle API/Connection       | `class-eb-settings-connection.php`, API handler classes  | Same                                   |
| Error Logging               | `class-eb-error-log.php`, Woo logs, server logs          | Same                                   |

---

**If you provide error log output or more details, you can pinpoint the exact cause.** 