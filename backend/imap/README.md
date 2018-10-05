# Z-Push-2.4.4-misc/IMAP

1) Modification of /backend/imap/imap.php to add a valid Message-ID field.  Any existing Message-ID value is replaced this new value.
This addresses the bug described in ZP=1288.  This function is performed at line 2504 and will function under all defined mail
mechanisms thusly:

<pre>
		$messageID = sprintf("<%s.%s@%s>", time(), base_convert(bin2hex(openssl_random_pseudo_bytes(8)), 16, 36), $_SERVER['SERVER_NAME']);
		if (array_key_exists("Message-Id",$headers)) {
			foreach (array("Message-Id") as $key) {
				$headers["Message-Id"] = $messageID;
			}
		} elseif (array_key_exists("Message-ID",$headers)) {
			foreach (array("Message-ID") as $key) {
				$headers["Message-ID"] = $messageID;
			}
		} elseif (array_key_exists("Message-id",$headers)) {
			foreach (array("Message-id") as $key) {
				$headers["Message-id"] = $messageID;
			}
		} else {
			$headers["Message-id"] = $messageID;
		}	
</pre>

2) Modifications of /backend/imap/imap.php, /lib/utils/utils.php, and /include/z_RFC822.php to fully support BCC addressing the bug
described in ZP-1292. Francisco's orginal method of munging all the recipients together IS preserved using the PHP mail() function.
This was done to support PHP on Windows.  This BCC implmentaton works for the SMTP mailer.  Operation is identical to that used in
the Thunderbird Email client.  This function is defined at line 2482, thusly:

<pre>
		if (empty($toaddr) && $sendingMethod == 'smtp') {
			foreach (array("Bcc") as $key) {
				if (!empty($headers[$key] && empty($toaddr))) {
				$toaddr = $fromaddr;
			    $headers["To"] = 'undisclosed-recipients: ;'; 
			    $recipients = array($toaddr);
				}
			}
		}
</pre>

NOTES: <b>2018-10-05:</b> imap.php changed for better case-handling of the BCC header.

