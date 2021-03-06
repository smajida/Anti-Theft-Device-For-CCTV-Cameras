# Anti-Theft-Device-For-CCTV-Cameras
## Abstract
<p>Internet of Things is all about connecting anything, anytime and anywhere. With the advent of the government taking up initiatives like Smart Cities, we as budding engineering students who are venturing into the new world, wanted to do a project that is in line with the current technology of the real world. We wanted to do a project that lets us give back something to the University that is providing our education and hence decided to do a project related to Smart Campus. Upon showing a proposal to the Director (E&amp;T), SRM University Kattankulathur, he discussed his concern regarding the safety of CCTV cameras inside the university campus and requested a project to be done regarding the same.</p>
<p> Hence, we decided to take it up as our minor project, leading to an “Anti-theft device for CCTV cameras”. This project focuses on providing just in time alerts to the concerned authorities upon the theft of the CCTV cameras inside the campus.</p>
<p>Two levels of security are used in this device.
  <ol>
    <li> The first level is a wire that connects the CCTV Camera and the controller. If the wire is not cut, the connection is close and current passes through the port to which the CCTV Camera is connected, to the controller. If the wire is cut, the connection is open and the current does not pass through the port to which the CCTV camera is connected to the controller, this happens when the CCTV camera and the anti-theft device are physically separated from each.</li>
    <li> The second level consists of two components, an IR Transmitter such as an IR LED, and an IR receiver circuit. The IR LED and the receiver as a combination can act as a proximity sensor. This combination is attached to the camera and as long as the camera and the wall are in close proximity, the camera is safe. When a person removes the camera, the wall and the camera are no longer in close proximity. This triggers the alerts.</li>
  </ol>
  <br>In order to send the alerts, we are using a GSM module that is connected to the Arduino to send SMS and make calls.The Raspberry Pi connects to the Internet and sends email and posts status of the CCTV camera to the online portal. Multiple Arduinos can be connected to a single Pi to allow scalability for real world usage. All the cameras in a single floor can have a common Raspberry Pi module through which they connect to the Internet.
</p>
##Components
<ol>
  <li>Arduino Uno , can buy <a href="http://www.amazon.in/s/ref=nb_sb_noss_2?url=search-alias%3Daps&field-keywords=arduino+uno">here</a>, there are a lot of counterfeits out there , learn more <a href="https://www.arduino.cc/en/Products/Counterfeit">here.</a></li>
  <li>Raspberry Pi, can buy <a href="http://www.amazon.in/Raspberry-Pi-RASPBERRY-model-Computer/dp/B01CCOXV34/ref=sr_1_1?ie=UTF8&qid=1474736047&sr=8-1&keywords=raspberry+pi">here.</a></li>
  <li>Breadboard , can buy <a href="http://www.amazon.in/s/ref=nb_sb_noss_2?url=search-alias%3Daps&field-keywords=breadboard&rh=i%3Aaps%2Ck%3Abreadboard">here</a></li>
  <li>Connecting wires , can buy <a href="http://www.amazon.in/RoboCraze-com-40pin-Dupont-Jumper-Wire/dp/B00WXE49TO/ref=sr_1_1?s=computers&ie=UTF8&qid=1474726756&sr=1-1&keywords=male+to+male+jumper">here</a></li>
  <li>GSM Module [SIMCOM SIM900A] , with an external antenna attached to it , can buy <a href="http://www.amazon.in/900A-MODEM-MODULE-ANTENNA-QUALITY/dp/B01BT54Y5G/ref=sr_1_1?s=computers&ie=UTF8&qid=1474726771&sr=1-1&keywords=SIM900A">here</a></li>
  <li>LED, can buy here<a href="http://www.amazon.in/COMPONENT7-100-Pc-5mm-White-Light-Emitting/dp/B01B0NY7BS/ref=sr_1_13?ie=UTF8&qid=1474736406&sr=8-13&keywords=LED"> </a></li>
  <li>Buzzer, can buy here<a href="http://www.amazon.in/Robo-India-Pizo-Buzzer-Set/dp/B00W7ATBYC/ref=sr_1_1?ie=UTF8&qid=1474736327&sr=8-1&keywords=buzzer"> </a></li>
  <li>Photodiode and IR Transmitter , commonly sold as <i>IR PAIR</i>, can buy here<a href=""http://www.amazon.in/IR-Pair-LED-Photo-Diode/dp/B01BRP3Y2C/ref=sr_1_2?ie=UTF8&qid=1474736310&sr=8-2&keywords=IR+PAIR"> </a></li>
  <li>Power source for the Arduino Uno , can buy <a href="http://www.amazon.in/techBerri-12V-1-5Amp-Adapter-Camera/dp/B011IMQD8Q/ref=sr_1_6?s=computers&ie=UTF8&qid=1474726869&sr=1-6&keywords=12v+adapter">here</a></li>
  <li>Power Source for the GSM Module , can buy <a href="http://www.amazon.in/techBerri-12V-1-5Amp-Adapter-Camera/dp/B011IMQD8Q/ref=sr_1_6?s=computers&ie=UTF8&qid=1474726869&sr=1-6&keywords=12v+adapter">here</a></li>
</ol>
##Circuit Diagram
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/CircuitDiagram.jpg">
<br>
Explanation for the circuit diagram is given in this <a href="https://drive.google.com/file/d/0B4ojjO5sVzx8VWUxaFlVX1dQR3M/view?usp=sharing">document</a>.
##Procedure
<ol>
<li>Make the connections as described in the cicuit diagram, the explanation for the same is provided in this <a href="https://drive.google.com/file/d/0B4ojjO5sVzx8VWUxaFlVX1dQR3M/view?usp=sharing">document</a>.</li>
<li>Download <a href="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/blob/master/IrWireCutGsmSMSCall.ino">IRWireCutSMSCall.ino</a> in this file, modfiy the "x" s with your cell phone number in the SMS function [Line 25] and with eighter your landline or cell phone number in the call fucntion [line 35] </li>
<li> Upload the ino file into your Arduino Board [Refer the <a href="https://drive.google.com/file/d/0B4ojjO5sVzx8Mk5iT2NQcFE4U0k/view?usp=sharing">Upload Code Into Arduino.pdf</a> file for the same]</li>
<li> Download <a href="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/blob/master/alert.py">alert.py</a> and in this script modilfy smtpUser smtpPasss to the user id and password of the GMail account from which you are sending the mail, make sure to disable secure login for that GMail account, else your login will fail.</li>
<li> Follow the steps in this <a href="https://www.youtube.com/watch?v=0kpGcMjpDcw">video</a> to setup ssmtp library for your Raspberry Pi  </li>
<li> Transfer the alert.py file to your Raspberry Pi , make sure the interface that connects to the internet is up and then run the python script <br><code>sudo python alert.py</code> </li> 
<li> Host a website using any hosting service, I used hostinger, and Upload the <a href="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/blob/master/esptalk.php">esptalk.php</a> and the <a href="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/blob/master/iscamerasafe.php">iscamerasafe.php</a> files into it </li>
<li> modfify the domain name in the notifyPortal function of the alert.py script to your new domain to which you just uploaded the code, and also in the mail content of the sendMail function </li>
<li> Provide power to the Aurdino , and Raspberry Pi and use it as shown in my <a href="https://www.youtube.com/watch?v=Ux5e9g4pWpc">YouTube Video</a>. </li>
##Snapshots
<b> Write cut </b>
<br>
Before
<br>
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/Pics/Wire%20Cut/Before.png"/>
<br>
During
<br>
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/Pics/Wire%20Cut/During.png"/>
<br>
After<br>
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/Pics/Wire%20Cut/After.png"/>
<br>
SMS Alert<br>
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/Pics/Wire%20Cut/After%20SMS.png"/>
<br>
Phone Call Alert<br>
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/Pics/Wire%20Cut/After%20Call.png"/>
<br>
<b> IR Pair </b>
<br>
Before<br>
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/Pics/IR/Before.png"/>
<br>
During<br>
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/Pics/IR/During.png"/>
<br>
After<br>
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/Pics/IR/After.png"/>
<br>
SMS Alert<br>
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/Pics/IR/After%20SMS.png"/>
<br>
Phone Call Alert<br>
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/Pics/IR/After%20Call.png"/>
<br>
<b>The EMmail and portal</b>
<br>
Before EMail
<br>
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/Pics/Email%20and%20Portal/Before%20Email.png" height="270" width="480">
<br>
The EMail<br>
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/Pics/Email%20and%20Portal/The%20Email.png" height="480" width="270">
<br>
Checking Status After EMail<br>
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/Pics/Email%20and%20Portal/Checking%20Status%20after%20Email.png" height="270" width="480">
<br>
Resetting via EMail Link<br>
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/Pics/Email%20and%20Portal/Resetting%20via%20Email%20Link.png" height="270" width="480">
<br>
After Resetting via EMail<br>
<img src="https://github.com/KaushikNeelichetty/Anti-Theft-Device-For-CCTV-Cameras/raw/master/Pics/Email%20and%20Portal/After%20Resetting%20via%20Email.png" height="270" width="480">
<br>
##HTTP GET REQUESTS FOR ALERTING PORTAL

http://domain.com/esptalk.php?safe=0&&camera=1 // writes unsafe into camera1.txt<br>
http://domain.com/esptalk.php?safe=1&&camera=1 // writes safe into camera1.txt<br>
http://domain.com/iscamerasafe.php?camera=1 //echo the content of camera1.txt on the website<br>
http://domain.com/iscamerasafe.php?camera=2 //echo the content of camera2.txt on the website<br>
