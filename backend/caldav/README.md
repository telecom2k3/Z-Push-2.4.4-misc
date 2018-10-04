# Z-Push-2.4.4-misc

1) Modification of /backend/caldav/caldav.php to add a sanity-check to not log a nuisance error "A non-numeric value encountered".
I'm not sure how the code gets there, but there is no action, so might as well bypass the error message.  Modified thusly at line 828:
<pre>
 						if (!empty($interval) && (is_integer($interval))) {
                        	$message->reminder = $interval->format("%i") + $interval->format("%h") * 60 + $interval->format("%a") * 60 * 24;
						}
</pre>

2) Incorporation of fix associated with ZP-1451 for /backend/caldav/caldav.php:
Added line: "$message->asbody->type = 2;" beneath the line "$message->asbody->data = StringStreamWrapper::Open($data);" on line 750.

3) FEATURE: Added a new configuration opt-on, "HTML_DETOX".  When set to "true", the DESCRIPTION (Note) field of a VEVENT or VTODO will
be stripped of HTML tags.  This is useful for making XML content from the native Windows 10 App more usable when viewing in other
Apps.

4) FEATURE: Added a new configuration option, "W10_FIX".  When set, a VEVENT's DTSTART date is set to the same as the DTEND date for
All-Day appointments.  This breaks proper operation of other Calendar Apps, so the default and recommended setting is "false".

