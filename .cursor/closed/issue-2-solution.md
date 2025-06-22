# Issue #2: Bridge Image Sync Issue - Solution

## Problem

The course image synchronization from Moodle to WordPress was failing, resulting in broken or empty images on the WordPress site. This issue also caused the synchronization process to get stuck in a loop.

## Root Cause

The root cause of the issue was traced to the `sync_course_image` function in the `plugins/edwiser-bridge/includes/class-eb-course-manager.php` file. The logic for appending the Moodle authentication token to the image URL was flawed. It specifically checked if the URL contained `?file=`, which is not always the case for Moodle's course image URLs. 

When a Moodle image URL had a different query string or no query string at all, the token was appended incorrectly, resulting in an invalid URL. The `file_get_contents` function would then fail to download the image, leading to a broken image in WordPress and causing the sync process to hang.

## Solution

The issue was resolved by modifying the URL construction logic in the `sync_course_image` function. The code was updated to check for the presence of a `?` character in the image URL, instead of the specific `?file=` string.

**File:** `plugins/edwiser-bridge/includes/class-eb-course-manager.php`

**Original Code:**
```php
if ( strpos( $course_image->fileurl, '?file=' ) !== false ) {
    $file_url = $course_image->fileurl . '&token=' . $token;
} else {
    $file_url = $course_image->fileurl . '?token=' . $token;
}
```

**Updated Code:**
```php
if ( strpos( $course_image->fileurl, '?' ) !== false ) {
    $file_url = $course_image->fileurl . '&token=' . $token;
} else {
    $file_url = $course_image->fileurl . '?token=' . $token;
}
```

This change ensures that the authentication token is always appended correctly to the image URL, regardless of its structure. This resolves the image download issue and, in turn, prevents the synchronization process from getting stuck in a loop.
