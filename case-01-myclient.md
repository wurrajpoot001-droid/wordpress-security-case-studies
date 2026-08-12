CASE STUDY #01 - WordPress Hardening + Brute-Force Detection Date: 13  Aug 2026 Client: Practice Client - myclient (Sanitized) Risk Before: HIGH | Risk After: LOW
--- FINDINGS BEFORE ---
    1. Outdated plugins: 3
    2. xmlrpc.php: Enabled
    3. Backup: Not configured
    4. Firewall: Not installed
    5. Default admin user: Yes
    6. Log Finding: 5x POST to wp-login.php from ::1 in 7 mins
--- EVIDENCE (LOG) --- ::1 - - [13/Aug/2026:00:19:06 +0500] "POST /myclient/wp-login.php HTTP/1.1" 200 6115 "http://localhost/myclient/wp-login.php" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/151.0.0.0 Safari/537.36" 
::1 - - [13/Aug/2026:00:19:19 +0500] "POST /myclient/wp-login.php HTTP/1.1" 200 6124 "http://localhost/myclient/wp-login.php" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/151.0.0.0 Safari/537.36" 
::1 - - [13/Aug/2026:00:19:27 +0500] "POST /myclient/wp-login.php HTTP/1.1" 200 6115 "http://localhost/myclient/wp-login.php" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/151.0.0.0 Safari/537.36" 
::1 - - [13/Aug/2026:00:19:33 +0500] "POST /myclient/wp-login.php HTTP/1.1" 200 6123 "http://localhost/myclient/wp-login.php" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/151.0.0.0 Safari/537.36" 
::1 - - [13/Aug/2026:00:19:41 +0500] "POST /myclient/wp-login.php HTTP/1.1" 200 6115 "http://localhost/myclient/wp-login.php" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/151.0.0.0 Safari/537.36"

--- ACTIONS TAKEN ---
    1. Backup live site with UpdraftPlus
    2. Restore to staging (XAMPP)
    3. Updated all plugins + core on staging
    4. Removed unused plugins/themes
    5. Disabled xmlrpc.php
    6. Installed Wordfence + configured firewall
    7. Set limit login to 3 attempts
    8. Setup backup to Google Drive
    9. Applied same to live site
--- RESULT AFTER --- Wordfence scan: 0 issues All plugins: Updated Backup: Configured daily Risk: HIGH -> LOW Downtime: 0 min
--- MITRE --- T1110 Brute Force T1190 Exploit Public-Facing Application
--- TOOLS --- Wordfence, UpdraftPlus, Apache access.log, wpvulndb.com
