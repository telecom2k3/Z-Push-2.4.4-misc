# Z-Push-2.4.4-misc

These are files containing various fixes and changed to Z-Push, Verson 2.4.4.

1) Modification of /lib/utils/timezoneutil.php to fix error messages resulting from missing Timezone information.  Ths is caused by the
Caldav backend.  It parses through the system timezones and attempts to find a match in timezoneutil.php which doesn't exist.  This poor timezone file was sorely in need of an update.
