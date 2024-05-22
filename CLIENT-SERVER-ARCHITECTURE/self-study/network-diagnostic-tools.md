<h2><b>Network Diagnostic Tools</b></h2>

<h3><b>Introduction</b></h3>

Every network administrator needs a good collection of tools in their toolbox, just like a professional plumber or electrician, to accomplish the job correctly. These tools can help you look into and resolve a wide range of problems as they crop up on your network, regardless of whether you're the new guy in the office or a seasoned pro.

When it comes to employing network troubleshooting tools, each IT professional has particular preferences, but there are a few basic ones that should be in everyone's toolbox.

A methodical, effective, and proactive approach to network troubleshooting is made possible by these network troubleshooting tools. By utilizing all the network diagnostic tools on this list, you can put together a workflow that will provide you with information on all potential network issues.

The life-saving network tools that every network administrator uses will be briefly introduced in this post. All the aforementioned tools are mostly command-line utilities that operate on various OSes. The top 8 network troubleshooting tools are as follows:

<ol>
<li>PuTTY

<li>Ping

<li>Tracert / Trace Route

<li>Nslookup

<li>Netstat

<li>ipconfig / ifconfig

<li>Pathping / MTR

<li>Route
</li></ol>

<h3><b>Ping</b></h3>

When managing a computer network, a user can use the fundamental Internet application known as ping (also known as Packet Internet or Inter-Network Groper) to test and confirm that a specific destination IP address is real and capable of accepting queries. The acronym was created to sound like what submariners called the sound of a returned sonar pulse.

A host computer that a user is attempting to connect to can be checked to see if it is operational using ping. A ping is a networking tool that may be used by any operating system (OS), including the majority of embedded network administration programs.

In order to function, Ping sends an Internet Control Message Protocol (ICMP) Echo Request to a specific network interface and then waits for a response. Ping signals are transmitted to a given address when a ping command is sent. The echo request is sent to the destination host, which then sends an echo reply packet in response.

To use Ping, you typically open a command-line interface (CLI) and type the following command:

```bash
ping <hostname_or_ip_address>
```
Example

```bash
ping steghub.com
```
Ping Output Explaination

<ol>
<li> Pinging <hostname> [IP address] with <size> bytes of data

<ul><li>Indicates the target host and the size of the packet sent.</li></ul>
<li> Reply from <IP address>: bytes=<size> time=<time>ms TTL=<ttl>
<ul>
<li>Reply from <IP address>: Confirms the host responded.</li>
<li>bytes=<size>: Size of the packet received.</li>
<li>time=<time>ms: Round-trip time for the packet.</li>
<li>TTL=<ttl>: Time to Live, indicating the number of hops the packet can take before being discarded.</li></ul>
<li>Statistics summary
<ul>
<li>Packets: Sent = x, Received = y, Lost = z ( loss), Shows the number of packets sent, received, and lost, along with the percentage of packet loss.</li>
<li>Approximate round trip times in milliseconds:
Minimum = xms, Maximum = yms, Average = zms

Provides the minimum, maximum, and average round-trip times.
</ol>
Interpreting Ping Results
<ul>
<li> Consistent low RTT: Indicates a stable and fast connection.</li>
<li>High RTT or packet loss: Suggests network congestion, routing issues, or hardware problems.</li>
<li> No reply: Could mean the host is down, there are firewall rules blocking ICMP, or the host is unreachable due to network issues.</li>
</ul>

<h3><b>Traceroute</b></h3>

A tool called Traceroute keeps track of the Internet path (gateway computers at each hop) that connects your computer to a given destination computer. Additionally, it computes and shows the duration of each hop. You can use this tool to locate areas of your internal network and the Internet with slow transfer rates. The Ping tool can be used to determine whether a host is present on the network before using Traceroute.

To use Traceroute, open a command-line interface and type the following command:

On Windows:

```bash
tracert <hostname_or_ip_address>
```

On Linux

```bash
traceroute <hostname_or_ip_address>
```
Example

```bash
tracert steghub.com
```

Traceroute Output Explaination

A typical Traceroute output includes several pieces of information:

<ul>
<li><b>Hop Number</b>: The sequence number of the hop in the route.</li>
<li><b>Router IP Address</b>: The IP address of the router at each hop.</li>
<li><b> Round-Trip Times</b>: Usually three time measurements (in milliseconds) for each hop to indicate the delay for packets to reach and return from that hop.</li>
</ul>

Example Traceroute Output:

```bash

 1    <time1> <time2> <time3> <Router_IP>
 2    <time1> <time2> <time3> <Router_IP>
 3    * * * Request timed out.
 4    <time1> <time2> <time3> <Router_IP>

```

Interpreting Traceroute Results

<ul>
<li><b>Consistent times across hops</b>: Indicates a stable route.</li>
<li><b>Increasing times</b>: Normal behavior, showing cumulative latency.</li>
<li><b>Large spikes in time</b>: Could indicate a congested or slow router.</li>
<li><b>Request timed out</b>: The router did not respond to the probe. This could be due to firewalls, the router being configured to not respond to traceroute, or packet loss.</li>
</ul>