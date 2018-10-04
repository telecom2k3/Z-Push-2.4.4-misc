# Z-Push-2.4.4-misc (timezoneutil.php and utils.php)

<b>1. Timezones</b>

New timezones added:
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

<b>2. Utils</b>

Modification of /lib/utils/utils.php line 586 to include the "undisclosed-recipients" and "Undisclosed recipients" headers without
logging error messages, thusly:
<pre>
return (bool) preg_match('#((U|u)ndisclosed[\-\s]recipients:|([a-zA-Z0-9_\-])+(\.([a-zA-Z0-9_\-])+)*@((\[(((([0-1])?([0-9])?[0-9])|(2[0-4][0-9])|(2[0-5][0-5])))\.(((([0-1])?([0-9])?[0-9])|(2[0-4][0-9])|(2[0-5][0-5])))\.(((([0-1])?([0-9])?[0-9])|(2[0-4][0-9])|(2[0-5][0-5])))\.(((([0-1])?([0-9])?[0-9])|(2[0-4][0-9])|(2[0-5][0-5]))\]))|((([a-zA-Z0-9])+(([\-])+([a-zA-Z0-9])+)*\.)+([a-zA-Z])+(([\-])+([a-zA-Z0-9])+)*)|localhost))#', $email);
</pre>
