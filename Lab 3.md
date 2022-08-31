<h3>Securing Access to the network devices</h3>

<pre>
  1. To configure the console password, connect console cable to your device console port and the other end to your PC’s serial port.
  
  2. After connect console cable to PC and router we can access the router via PC.
  
  4. Configure the console password
  
C(config)#line console 0
C(config-line)#password c543
C(config-line)#login
  
  5. Configure the Telnet password
  
C(config)#line vty 0 4
C(config-line)#password T654
C(config-line)#login


*** After setting these console and Telenet passowrd it is visible to use after running the C# show run
*** After that if we went to user mode we have to enter the console password to go privilleged mode

7. From your PC you can use the command prompt to access the CLI via IP network.
But you will not succeed this attempt and will see an error message saying, “No
password set”. To overcome this error, you have to configure Privilege level
password to the device. 

C(config)#enable secret S432
C(config)#enable password E321
C(config)#

**** To encypte all the console / Telenet / enable password we used --service password encrypted

C(config)#service password-encryption




</pre>
