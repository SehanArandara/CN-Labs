<h3> Activity 4 </h3>
1. changing host name
<pre>
1. Changing the hostname of a router.
  a. Add a router to the packet tracer work space.
  b. Configure the hostname of the router to Malabe (Hint: You should be in global
    configuration mode and use the help command). 
<br>
Malabe>enable
Malabe#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Malabe(config)#hostname Malabe
Malabe(config)#
Malabe#

</pre>

<h3> Create password </h3>
<pre>
2. Set a password for privileged mode.
  a. Configure the privilege mode password to malabe123
  <br>
    Malabe(config)#
    Malabe(config)#enable password malabe123
<br>
3. Set a secret for privileged mode.
  a. Configure the privilege mode secret to malabe987
  <br>
    Malabe(config)#
    Malabe(config)#enable secret malabe987
<br>
 **** we can show the password
 Malabe#
Malabe#show run
Building configuration...

Current configuration : 723 bytes
!
version 16.6.4
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Malabe
!
!
!
enable secret 5 $1$mERr$q2ubpa.VoEh6NxvPlRex1.
enable password malabe123

<br>
What is difference between privilege mode password and secret? 
  - we can view password it is not encypted but secret password is not visible thats means
    it is encrypted.. only router creter only knows that password
In case both are configured, which will have the priority? 
  - Secret password because it has more security
  
 
</pre>
<pre>
4. Set a message-of-the-day banner for the router.
  a. Configure message-of-the-day bannerto !!!Authorized Personal Only!!! 
  <br>
  Malabe>enable
Password: 
Password: 
Malabe#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Malabe(config)#banner motd @!!! authorized persons ony !!! @
Malabe(config)#

**** to display the banner we have to go user mode
</pre>

<pre>
5. Remove the privilege mode password (Hint: use the no keyword).
<br>
  Malabe>enable
  Password: 
  Password: 
  Malabe#config t
  Enter configuration commands, one per line.  End with CNTL/Z.
  Malabe(config)#no enable password
  Malabe(config)#

</pre>

<h3>Activity 7 - IP Address Configurations& Static and Default Routing </h3>
<img src="https://github.com/SehanArandara/rash/blob/main/Capture.JPG" >
<pre>
1. Assign IP address and subnet mask to PC 

</pre>
<pre>
2. Assign IP addresses to ports(Gatways)
<h5> Router 4 </h5>
Router>enable
Router#config t
Router(config)#int Fa0/0
Router(config-if)#ip address 192.168.10.1 255.255.255.0
Router(config-if)#no shutdown

<br>

Router(config)#int Se2/0
Router(config-if)#ip address 10.1.0.1 255.0.0.0
Router(config-if)#no shutdown

<br>
<h5> Router 5 </h5>

Router>enable
Router#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#int Se3/0
Router(config-if)#ip address 10.1.0.2 255.0.0.0
Router(config-if)#no shutdown
<br>

Router(config)#int Se2/0
Router(config-if)#ip address 11.2.0.1 255.0.0.0
Router(config-if)#no shutdown

<br>
Router(config-if)#exit
Router(config)#int Fa0/0
Router(config-if)#ip address 192.168.11.1 255.255.255.0
Router(config-if)#no shutdow

<h5> Router 0 </h5>

Router>enable
Router#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#int Se2/0
Router(config-if)#ip address 11.2.0.2 255.0.0.0
Router(config-if)#no shutdown


Router(config)#int Fa0/0
Router(config-if)#ip address 192.168.12.1 255.255.255.0
Router(config-if)#no shutdown



2. verify the LAN by using  ping command in CLI

3.View the routing table with directly connected networks.

<img src="https://github.com/SehanArandara/rash/blob/main/1.JPG">


4. Enable inter LAN communication by configuring Static routing and Default routing

--- Router 4 ----
Router(config)#ip route 192.168.11.0 255.255.255.0 10.1.0.2
Router(config)#ip route 192.168.12.0 255.255.255.0 10.1.0.2

--- Router 5 ---
Router(config)#ip route 192.168.10.0 255.255.255.0 10.1.0.1
Router(config)#ip route 192.168.12.0 255.255.255.0 11.2.0.2

--- Router 0 --- 
Router(config)#ip route 192.168.11.0 255.255.255.0 11.2.0.1
Router(config)#ip route 192.168.10.0 255.255.255.0 11.2.0.1

5.Analyze the entries of the routing table again. 
  --- there will be changes in route table before and now
  
  
6.

</pre>
