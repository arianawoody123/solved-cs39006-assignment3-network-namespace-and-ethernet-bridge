Download Link: https://assignmentchef.com/product/solved-cs39006-assignment3-network-namespace-and-ethernet-bridge
<br>
You’ll learn about the concept of network namespace in this assignment. A network namespace is a logical copy of the Kernel network protocol stack, where you can configure its own routing policies, firewall rules, and devices. A network namespace is particularly used for supporting network virtualization; for example, in the case of containers, a network namespace is used to support isolation in the network protocol stack between two containers. You may check the followings to know more about network namespace —

<ol>

 <li><a href="https://man7.org/linux/man-pages/man8/ip-netns.8.html#:~:text=A%20network%20namespace%20is%20logically,namespace%20from%20the%20init%20process">https://man7.org/linux/man-pages/man8/ip-netns.8.html#:~:text=A%20network%2</a></li>

</ol>

<a href="https://man7.org/linux/man-pages/man8/ip-netns.8.html#:~:text=A%20network%20namespace%20is%20logically,namespace%20from%20the%20init%20process">0namespace%20is%20logically,namespace%20from%20the%20init%20process</a>.​

<ol start="2">

 <li><a href="https://blog.scottlowe.org/2013/09/04/introducing-linux-network-namespaces/">https://blog.scottlowe.org/2013/09/04/introducing-linux-network-namespaces/</a></li>

</ol>

In this assignment, you have to write two shell scripts to create two virtual networks and perform a set of experiments. The details follow.

<strong>PART – A: </strong>

Create two network namespaces and attach two virtual ethernet (veth) interfaces with the two namespaces. Logically configure the two network namespaces to create a simple network as follows.

Configure the two interfaces so that you can ping one interface from the other. You need to write a single shell script to accomplish the complete task (except ping). Once we execute the shell script, it should create the virtual network and configure the interfaces accordingly, so that the devices can be pinged from each other.

You need to submit this shell script with name assignment3_partA.sh​ .​

<strong>PART – B:  </strong>

Now, write a shell script to create a virtual network as follows.

Here R works as a bridge to connect three networks. The IPs of the six veth​ interfaces are as follows:

veth1:​ 10.0.10.X/24 veth2:​ 10.0.10.1/24 veth3:​ 10.0.20.1/24 veth4:​ 10.0.30.1/24 veth5:​ 10.0.30.X/24 veth6:​ 10.0.20.X/24

Where X is the last two digits of your roll number.

Through your shell script, configure the namespaces and devices, so that H1, H2, and H3 can ping each other. Note the following points —

<ol>

 <li>You need to configure Ethernet bridges at R so that it can interconnect the three networks (check the brctl​ command-line tool that is used to configure Ethernet bridges).</li>

 <li>You need to enable IP forwarding at R so that the packets from each network can be forwarded to the other network. Use the sysctl​ command over the network interface of R to set ipv4.ip_forward=1​ .​ ​This will configure the protocol stack at R to enable IP packet forwarding.</li>

</ol>

You need to submit this shell script with name assignment3_partB.sh​ .​


