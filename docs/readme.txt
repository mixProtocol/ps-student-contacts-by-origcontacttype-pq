Students - Contacts By Original Contact Type PowerQuery

Description:
This plugin provides a PowerQuery that allows for exporting PS12 "unlimited" contact data, by-student, for those contacts that have been matched to an original contact type (Mother, Father, Guardian, Emergency1-3). This can be used to feed messaging platforms like SchoolMessenger via SFTP, or to potentially import into PowerSchool Special Education (via localfile-to-DCT).

For each contact assigned to an OriginalContactType, this pulls their first "Preferred" home, mobile, and work phone numbers, if they exist, from the list of phone numbers. If there's no preferred, then it returns the first instance of the phone number type (ie: mobile) from the list. It does a similar thing for "Current" emails, looking first for the one flagged as "Primary" but otherwise returning the first "Current" in the list.  The StreetAddress data is first-in-list, regardless of type (Home, Mailing or NULL); there's no PS-native flag for "Preferred" or "Primary".

The query also returns relevant information from the student record (including schoolId, grade_level, homeroom, email, home_ and Mail_addresses, etc...). Field names are prefixed by the originalContactType or "Student_", as appropriate.

Two Data sets are currently provided:

Students: Contacts by OrigContactType - Comprehensive 6 (M,F,G,E1,E2,E3) includes Email, Phones and Street Address information for all six (6) original contact types,
Students: Contacts by OrigContactType - Email and Phones 3 (M,F,G) includes only Email and Phone information for only three (3) primary original contact types.  This may be enough for mass-messaging platforms (like School Messenger).

Notes:
All students are returned in the results, regardless of Enroll_Status.  Filter as needed in Data Export Manager.
Contacts, addresses, etc... are returned regardless of whether they're 'active' or have an 'end date' in the past.  A future release will filter these to ensure that only active data is included,

Performance: Given the number of tables that are joined and the number of fields that are returned, these are processor-intensive queries (especially the "Comprehensive 6") that can take several long minutes to complete (5 or more). I can include less-weighty data sets in a future release if/as needed.
Installation:
Install in System > System Settings > Plugin Management Configuration

Do not unzip the plugin. Install the entire zip file. Be sure to enable the plugin once it's installed.

If you are updating, you can now click on the Plugin name and then use the Update button, and then browse to the new file and click Submit and it will then load the update and then ask you to enable it.

Instructions:
Once the plugin is installed and enabled, the new datasets can be found in Data Export Manager (under the "Additional Data Sets" category).  The query names begin with "Students: Contacts by OrigContactType..."