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
