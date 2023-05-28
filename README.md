<?php


 extract($_POST);

$to = ' janakivallabhpurchase@gmail.com';		/*enter ur email address on which u want all mails*/
$subject = 'Janaki Vallabh Foods';		/*Enter ur Subject */
$msg = '<html>
<head>
<title>Janaki Vallabh Foods</title>
</head>

<body>
<h2>Janaki Vallabh Foods</h2>
<table cellspacing=\"4\" cellpadding=\"4\" border=\"1\" align=\"center\">
 
 <tr>
 <td align=\"center\">Full name</td>
 <td align=\"center\">'.$form_name.'</td>
  </tr>
  <tr>
  <td align=\"center\">Email</td>
  <td align=\"center\">'.$form_email.'</td>
  </tr>
  <tr>
 <td align=\"center\">Phone number</td>
 <td align=\"center\">'.$form_number.'</td>
 </tr>
  <tr>
 <td align=\"center\">Message</td>
 <td align=\"center\">'.$form_message.'</td>
 </tr>

</table>
</body>
</html>';

// Make sure to escape quotes

$headers  = 'MIME-Version: 1.0' . "\r\n";
$headers .= 'Content-type: text/html; charset=iso-8859-1' . "\r\n";
$headers .= 'From: Janaki Vallabh Foods < janakivallabhpurchase@gmail.com>' . "\r\n";		
	/*domain name and support email enter */

if (mail($to, $subject, $msg, $headers))
{
 ?>
   <script>
 alert("Thanks for Query.  We will get in touch with you shortly");
 window.location.href="index.php" ;		/*return on page which u want*/ 
 </script>
<?php
}else{ ?>

 <script>
 alert("Message not sent, Please try again.");
 window.location.href="index.php" ;		/*return on page which u want*/ 
 </script>

<?php } ?>

