# uiXpress for Tutor LMS

Want to turn the WordPress backend into a modern, dedicated instructor dashboard with built-in theme options and many other customization opportunities? One that is only applied to the instructor role giving them safe access to backend pages not available in the frontend, but removing unsafe and irrelevant backend pages for a nicer UX? This free uiXpress import does just that!

The repository has two files:

| File                           | What it is                   |
| ------------------------------ | ---------------------------- |
| `uixpress-settings.json`       | uiXpress settings export     |
| `Instructor Backend Menu.json` | uiXpress Menu Creator export |

These uiXpress import files create a modern, dedicated instructor backend for Tutor LMS. It also includes menu items that link to Tutor LMS frontend dashboard pages that do not have analogous backend pages. uiXpress is required.

## What the menu includes

The menu applies to the `tutor_instructor` role only.

**Course work.** Courses, Announcements, Quiz Attempts, Assignments, Q&A, and Certificates.

**Live classes.** Google Meet and Zoom.

**Libraries.** Content Bank, Media Library, and H5P Content.

**Account.** Analytics, Profile, Reviews, Withdrawals, and Settings.

Courses, Announcements, Quiz Attempts, and Content Bank already limit their lists to the current instructor. Assignments, Q&A, Google Meet, and Zoom are included with known gaps on individual records. Those gaps are described under TutorPress below.

Certificates, Analytics, Profile, Reviews, Withdrawals, and Settings are Tutor frontend dashboard screens. Their links use the dashboard slug `dashboard` in the export file (`/dashboard/analytics/`, `/dashboard/account/profile/`, and so on). If the site uses another dashboard slug, update those four links in **uiXpress → Menu Creator → Instructor Backend Menu** after import.

Icons on the Tutor menu items are Tutor LMS icons, stored in each item as an SVG data URI.

The export hides admin menu items not relevant to the instructor backend. However, the site admin will have to hide other admin menu items that aren't already hidden by this export.

## What the settings include

`uixpress-settings.json` is the uiXpress settings import. The shell is turned off for all default roles except `tutor_instructor` but the site might have other roles that will need to be excluded. To do so, navigate to **uiXpress → Settings → General** and review the "Disable theme" setting. Site-specific, and theme-related settings are either not configured or left as defaults in order to allow site owners to complete those. The file also sets the dashboard and search post types appropriate for an instructor backend.

## Download the import files

1. Open [indigetal/uixpress-tutor-lms](https://github.com/indigetal/uixpress-tutor-lms).
2. Open `uixpress-settings.json`. On the file page, use the download icon next to **Raw**.
3. Open `Instructor Backend Menu.json` and download it the same way.

You can also download both files at once. On the repository page, choose **Code**, then **Download ZIP**, and use the two JSON files inside the archive.

Direct links for the files on `main`:

- [uixpress-settings.json](https://github.com/indigetal/uixpress-tutor-lms/blob/main/uixpress-settings.json)
- [Instructor Backend Menu.json](https://github.com/indigetal/uixpress-tutor-lms/blob/main/Instructor%20Backend%20Menu.json)

## Import the settings

1. In the WordPress admin, open **uiXpress → Settings**.
2. Choose the **Import settings** icon at the top of the left hand "Settings" column and select `uixpress-settings.json`.
3. **Save changes**.

## Import the menu

1. Open **uiXpress → Menu Creator**.
2. Create a new menu or open an existing menu that should become the instructor menu.
3. In the selected menu, open the vertical elipsis and choose **Import**. Select `Instructor Backend Menu.json`.
4. Confirm **Import menu**.
5. In the menu settings, set **Status** to **Active**.
6. Click **Save**.

## TutorPress

We have notified Tutor LMS of instructor-access issues that we have discovered. If no fixes are made in a future update, the issues will be resolved in [TutorPress](https://github.com/indigetal/tutorpress). However, the export files will not include these additional menu items for security reasons. Even after TutorPress provides the checks, an administrator will still have to manually add the fixed pages to their uiXpress menu configuration.

Several pages already on the menu, including Assignments, Q&A, Google Meet, and Zoom still need additional permissions work but their lists are already limited to the instructor. TutorPress will complete those checks.

Google Classroom has no instructor filter on its list. Students, Enrollment, Gradebook, Reports, and Withdraw Requests also have no instructor filter, and they require the `manage_tutor` capability. `tutor_instructor` does not have that capability. A later TutorPress update will scope those lists so the pages can be added to this menu. Some actions on those pages will reamin limited to administrators.
