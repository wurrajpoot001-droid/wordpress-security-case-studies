# Case Study #04 - Disaster Recovery - UpdraftPlus Backup & Restore

## Overview
Client site completely broken - "Cannot select database" error after hosting crash. All database tables dropped. Restored 100% with UpdraftPlus backup.

## Before
- Site shows: "Cannot select database"
- Database tables dropped - 0 tables in phpMyAdmin
- Client panic - No backup with host

## Backup Evidence (Before Disaster)
- UpdraftPlus backup: 145MB total
- 5 files: backup_2026-08-09-1952_My_Test_Site_... - plugins.zip, themes.zip, uploads.zip, db.gz, others.zip
- Location: wp-content/updraft/ + Google Drive - 2 copies
- Time: 2.5 mins
-safely_taken_backup.png
<img width="1362" height="586" alt="safely taken backup" src="https://github.com/user-attachments/assets/42db9ec5-7f88-4008-bec5-1157d181e87d" />


## Disaster Created (For Lab)
- Dropped all tables via phpMyAdmin > Drop
- Error: "Cannot select database - Are you sure it exists? Does user root have permission?"
- site_break.png
- <img width="1358" height="674" alt="site break" src="https://github.com/user-attachments/assets/9d3bf6ac-841b-41eb-b8f5-6617355c842b" />


## Restore Process
### Method 1: One-Click (When wp-admin works) - 04:12
- UpdraftPlus > Existing Backups > Restore > Select All > Restore
- Time: 04:12 secs

### Method 2: Manual (When wp-admin dead - Used in this case)
1. File Manager > wp-content/updraft/ > 5 zips present
2. Extract db.gz to db.sql via 7-Zip
3. phpMyAdmin > myclient_2 DB > Import > Choose db.sql > Import successful - 254 tables restored
4. File Manager > Extract plugins.zip, themes.zip, uploads.zip to wp-content/ > Overwrite
5. Fix wp-config.php permissions 600
6. Site load successfully - Dashboard working

## After
- Screenshot: import_successful.png:
- <img width="1352" height="675" alt="import successful" src="https://github.com/user-attachments/assets/b56c704c-236e-48c6-86e7-35537621e2b6" />

- site_load_successfully.png - WP Dashboard working, UpdraftPlus installed
- <img width="1365" height="685" alt="site load successfully" src="https://github.com/user-attachments/assets/c676f3b9-9fff-489a-81a9-b943aa6dbb3c" />

- Wordfence Scan: 0 malware - Clean
- Result: 100% Restored - 0 Data Loss

## Tools Used
- UpdraftPlus Free
- cPanel File Manager / XAMPP File Explorer
- phpMyAdmin
- Wordfence for final scan

## Time
- Backup: 2.5 mins
- Restore: 04:12
- Total: <7 mins

## Evidence
- 4 screenshots Before/After + Collage
- Timer: 04:12
- <img width="1660" height="1540" alt="case-study-updraft-collage-linkedin-fb" src="https://github.com/user-attachments/assets/6fc2fa49-0d0f-44f7-98c4-9479a05d2b02" />


## Value
- This is $100 package - Backup + Disaster Recovery + 7-day guarantee
