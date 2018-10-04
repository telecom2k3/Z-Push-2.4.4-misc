# Z-Push-2.4.4-misc

These are files containing various fixes and changed to Z-Push, Verson 2.4.4.

1) Modification of /lib/utils/timezoneutil.php to fix error messages resulting from missing Timezone information.  Ths is caused by the
Caldav backend.  It parses through the system timezones and attempts to find a match in timezoneutil.php which doesn't exist.  This poor timezone file was sorely in need of an update.

2) Modification of /backend/caldav/caldav.php and the config.php file.  Two new configuration options are available, including 
HTML_DETOX to make Windows 10 Mail App events more usable. This also fixes a nuisance error that gets logged a lot.  This also incorporates the fix associated with ZP-1451.

3) Modification of /backend/imap/imap.php to add a valid Message-ID field. Any existing Message-ID value is replaced this new value. This addresses the bug described in ZP=1288. 

