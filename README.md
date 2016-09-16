# Anti-Theft-Device-For-CCTV-Cameras
## Abstract
Internet of Things is all about connecting anything, anytime and anywhere. With the advent of the government taking up initiatives like Smart Cities, we as budding engineering students who are venturing into the new world, wanted to do a project that is in line with the current technology of the real world. We wanted to do a project that lets us give back something to the University that is providing our education and hence decided to do a project related to Smart Campus. Upon showing a proposal to the Director (E&amp;T), SRM University Kattankulathur, he discussed his concern regarding the safety of CCTV cameras inside the university campus and requested a project to be done regarding the same. Hence, we decided to take it up as our minor project, leading to an “Anti-theft device for CCTV cameras”. This project focuses on providing just in time alerts to the concerned authorities upon the theft of the CCTV cameras inside the campus.  Two levels of security are used in this device. The first level is a wire that connects the CCTV Camera and the controller. If the wire is not cut, the connection is close and current passes through the port to which the CCTV Camera is connected, to the controller. If the wire is cut, the connection is open and the current does not pass through the port to which the CCTV camera is connected to the controller, this happens when the CCTV camera and the anti-theft device are physically separated from each. The second level consists of two components, an IR Transmitter such as an IR LED, and an IR receiver circuit. The IR LED and the receiver as a combination can act as a proximity sensor. This combination is attached to the camera and as long as the camera and the wall are in close proximity, the camera is safe. When a person removes the camera, the wall and the camera are no longer in close proximity. This triggers the alerts.  In order to send the alerts, we are using a GSM module that is connected to the Arduino to send SMS and make calls. The Raspberry Pi connects to the Internet and sends email and posts status of the CCTV camera to the online portal. Multiple Arduinos can be connected to a single Pi to allow scalability for real world usage. All the cameras in a single floor can have a common Raspberry Pi module through which they connect to the Internet.
##Circuit Diagram
<img src="">
##Procedure
<ol>
<li>Make the connections as described in the cicuit diagram, the explanation for the same is provided in this <a href="">document</a>.</li>
<li>In the IRWireCutSMSCall.ino file, modfiy the "x" s with your cell phone number in the SMS function [Line 25] and with eighter your landline or cell phone number in the call fucntion [line 35] </li>
<li> Upload the ino file into your Arduino Board [Refer the Upload Code Into <a href="">Arduino.docx</a> file for the same</li>
<li> In the alert.py script modilfy smtpUser smtpPasss to the user id and password of the GMail account from which you are sending the mail, make sure to disable secure login for that Gmail account, else your login will fail.</li>
5] Follow the steps in this video to setup ssmtp library for your Raspberry Pi https://www.youtube.com/watch?v=0kpGcMjpDcw
6] Transfer the alert.py file to your Raspbeery Pi , make sure the interface that connects to the internet is up and then run the python script "sudo python alert.py" 
7] Host a website using any hosting service, I used hostinger, and Upload the esptalk.php and the iscamerasafe.php files into it
8] modfify the domain name in the notifyPortal function of the alert.py script to your new domain to which you just uploaded the code, and also in the mail content of the sendMail function
9] Provide power to the Aurdino , and Raspberry Pi and use it as shown in the YouTube Video. 

GET REQUESTS FOR ALRTING PORTAL

http://domain.com/esptalk.php?safe=0&&camera=1 // writes unsafe into camera1.txt
http://domain.com/esptalk.php?safe=1&&camera=1 // writes safe into camera1.txt
http://domain.com/iscamerasafe.php?camera=1 //echo the content of camera1.txt on the website
http://domain.com/iscamerasafe.php?camera=2 //echo the content of camera2.txt on the website
