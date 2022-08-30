<img src="https://github.com/SehanArandara/rash/blob/main/Capture2.JPG">

<h3> 1.Re name the network devices as follows</h3>

router 1 - > SLIIT <br>
switch 1 -> IT <br>
switch 2 -> CSN <br>

<h5> Commonds </h5>

router 1 ---->
<pre>
Router>enable
Router#config t
Router(config)#hostname SLIIT
SLIIT(config)#
</pre>

switch 1 ---->
<pre>
Router>enable
Router#config t
Router(config)#hostname SLIIT
SLIIT(config)#
</pre>

switch 2 --->
<pre>
Router>enable
Router#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#hostname SLIIT
SLIIT(config)#
</pre>


<h3>Assign the IP addresses to the PCs and interfaces as follows:</h3>
<img src="https://github.com/SehanArandara/rash/blob/main/Capture.JPG">
<pre>
** Router is used to Connect LAN to WAN or MAN or another LAN
** Router contains ports (interfaces) reach interfaces has a gatway address
** The IP address of router part which is connected to a particular LAN is called The "Gateway IP address" of the LAN
</pre>
** commonds to add IP address to interfaces
<pre>

SLIIT>enable 
SLIIT#config t
SLIIT(config)#int Fa0/0
SLIIT(config-if)#ip address 192.168.100.1 255.255.255.0
SLIIT(config-if)#no shutdown 

SLIIT(config-if)#exit

SLIIT(config)#int fa0/1
SLIIT(config-if)#ip address 192.168.200.1 255.255.255.0
SLIIT(config-if)#no shutdown

</pre>
<pre>
**To check show info about router (we can double checked)
SLIIT#show ip interface br
SLIIT#show ip interface brief 
<br>

Interface              IP-Address      OK? Method Status                Protocol 
FastEthernet0/0        192.168.100.1   YES manual up                    up 
FastEthernet0/1        192.168.200.1   YES manual up                    up 
Vlan1                  unassigned      YES unset  administratively down down
</pre>

** Assign IP address to computer(static way)
<pre>
click source PC-> desktop-> IP comfiguration
<img src="https://github.com/SehanArandara/rash/blob/main/3.JPG">
</pre>








