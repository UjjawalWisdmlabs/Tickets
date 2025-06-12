# Problem 1: User Not Enrolled After Product Purchase (Edwiser Bridge + WooCommerce)

## Context
When a user purchases a WooCommerce product that is linked to a Moodle course via Edwiser Bridge (Free or Pro), the expected behavior is that the user is automatically enrolled in the corresponding Moodle course after a successful purchase.

## Symptoms
- User completes checkout and payment in WooCommerce.
- Order appears in WooCommerce, but the user is not enrolled in the Moodle course.
- No enrollment email is sent, or user cannot access the course.

## Where This Typically Occurs
- Edwiser Bridge (Free or Pro) with WooCommerce integration.
- Most often seen when:
  - Order status is not set to "Completed" automatically.
  - Product–course mapping is missing or incorrect.
  - There are issues with the Moodle API connection.
  - There are plugin conflicts or misconfigurations.

## Impact
- Users do not get access to purchased courses.
- Support requests increase due to failed enrollments.
- Revenue and user experience are negatively affected.

---
See `solution1.md` for a step-by-step troubleshooting and resolution guide. 