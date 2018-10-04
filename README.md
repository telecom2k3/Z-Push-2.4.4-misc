# Z-Push-2.4.4-misc

These are files containing various fixes and changed to Z-Push, Verson 2.4.4.

1) Modification of /lib/utils/timezoneutil.php to fix error messages resulting from missing Timezone information.  Ths is caused by the
caldav.php backend looking through the system timezones and attempting to find a match in timezoneutil.php.  This timezone file is
sorely in need of an update.  New timezones added:
<pre>
America/Fort_Nelson
America/Punta_Arenas
Antarctica/Troll
Asia/Atyrau
Asia/Barnaul
Asia/Chita
Asia/Famagusta
Asia/Khandyga
Asia/Srednekolymsk
Asia/Tomsk
Asia/Ust-Nera
Asia/Yangon
Australia/Eucla
Australia/Lord_Howe
Europe/Astrakhan
Europe/Busingen
Europe/Kirov
Europe/Saratov
Europe/Ulyanovsk
Pacific/Bougainville
Pacific/Chatham
Pacific/Fakaofo
Pacific/Kiritimati
Pacific/Marquesas
Pacific/Norfolk
</pre>
