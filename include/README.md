# Z-Push-2.4.4-misc/RFC-822

Modification of /include/z_RFC822.php at line 575 to remove checking of ":" and ";" characters, thusly:
<pre>
        // if (preg_match('/[][()<>@,;\\:". ]/', $atom)) {
           if (preg_match('/[][()<>@,\\". ]/', $atom)) {
</pre>

Yes, a modification of this regex. My take is that there are standards, and then there are the ways the industry implements those
standards.  Adding a little "Swedish" here is probably a good thing.
