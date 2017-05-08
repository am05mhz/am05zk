# am05zk
PHP library for communicating with ZKFinger SDK

## License
The software licensed under the [MIT license](http://opensource.org/licenses/MIT)

# Notes
This project only support a subset of the undocumented (or poorly documented) ZKFinger SDK.
The SDK have lots of version that differs in the transmitted data structure, 
hence it would need some adjustment according to your device.

#Requirements
This library relies on PHP SOAP, PHP Socket, and PHP cURL extentions to work properly.

# Usage

```PHP

include 'am05zk.php';

$ip = '10.11.12.13';                     //ip of fingerprint scanner

$zk = new am05zk($ip);

if ($zk->connect()){
	//connection successfull
	
	$version = $zk->get_version();       // get the firmware version
	$users = $zk->get_users();           // get list of users
	$attendance = $zk->get_attendance(); // get all attendance records in the device
	$zk->clear_attendance();             // clear all the attendance record in the device
	
	$zk->disconnect();
} else {
	//connection fail
}