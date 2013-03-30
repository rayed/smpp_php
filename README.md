
#SMPP Client written PHP#
 
##Usage##
	<?php

	include 'class.smpp.php';

	$src  = "phone_number"; // or text 
	$dst  = "phone_number";
	$message = "Test Message";

	$s = new smpp();
	$s->debug=1;

	// $host,$port,$system_id,$password
	$s->open("10.0.0.5", 12345, "system_id", "password");

	// $source_addr,$destintation_addr,$short_message,$utf=0,$flash=0
	$s->send_long($src, $dst, $message);

	/* To send unicode 
	$utf = true;
	$message = iconv('Windows-1256','UTF-16BE',$message);
	$s->send_long($src, $dst, $message, $utf);
	*/

	$s->close();
	?>

