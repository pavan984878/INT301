# INT301
Open Source Project

### Question
<h2><b>Implement a network miner tool to detect the operating system, sessions and open ports through
packet sniffing and investigate the network traffic.</b></h2>
___

<h3>In this project, I will be implementing a network miner tool using Wireshark to detect the operating system, sessions, and open ports through packet sniffing and investigating network traffic. Wireshark is a popular open-source packet analyzer that allows us to capture and analyze network traffic in real-time. With Wireshark, I will be able to monitor and analyze the packets flowing through the network and gain valuable insights into the devices, protocols, and services being used.

To detect the operating system, I will be using Wireshark's built-in functionality to analyze the packets and identify the operating system being used by each device on the network. This will involve analyzing the various network protocols and fingerprinting techniques to determine the specific operating system version and vendor.

To detect sessions, I will be using Wireshark to capture and analyze the various network sessions taking place on the network. This will involve analyzing the various network protocols such as TCP, UDP, and ICMP to identify the start and end of each session, the data being transmitted, and the devices involved in the session.

To detect open ports, I will be using Wireshark to capture and analyze the various network packets to identify the ports that are being used by various devices on the network. This will involve analyzing the various network protocols such as TCP, UDP, and ICMP to identify the ports that are being used by different services and applications.

Overall, the project will involve using Wireshark to capture and analyze network traffic in real-time and gain valuable insights into the devices, protocols, and services being used on the network. By implementing this network miner tool, we will be able to detect the operating system, sessions, and open ports through packet sniffing and investigate the network traffic.</h3>
<img src="1.png" alt="WireShark Installation" >
___
<h3>Finding the operating system</h3>
<p>To find the operating system using the Time to Live (TTL) in Wireshark, you can follow these step-by-step procedures:

Start Wireshark: Open Wireshark on your computer.

Capture network traffic: Capture the network traffic you want to analyze by selecting the appropriate network interface in Wireshark.

Filter packets: Apply a filter to the captured packets to reduce the amount of data you need to analyze. To filter the packets by the TTL field, use the following filter expression: "ip.ttl==128". This will show all packets with a TTL of 128, which are commonly used by certain operating systems.

Observe TTL values: Examine the TTL values of the packets that are displayed in the capture window. The TTL values are displayed in the Time to Live column.

Determine the operating system: Compare the TTL values of the packets to the TTL values of known operating systems. Different operating systems use different TTL values, so by comparing the TTL values of the packets to known values, you can determine the operating system.

Repeat for other packets: Repeat this process for other packets to get a better idea of the operating systems being used on the network.

sessions.png

By following these steps, you can use Wireshark to determine the operating system being used on a network by analyzing the TTL values of the captured packets.</p>
<img src="Screenshot (8).png" alt="Finding Operating System Using Time To Live" >
___
<h3>Finding TCP Session</h3>
The Time to Live (TTL) field in the IP header can be used to identify TCP sessions in Wireshark. Here's a step-by-step procedure to find TCP sessions using TTL:

Open Wireshark and load the capture file containing the network traffic you want to analyze.

Filter the traffic to display only TCP packets. You can do this by typing "tcp" in the filter box.

Look for packets with different TTL values. The TTL field in the IP header specifies the maximum number of hops a packet can take before being discarded. Each operating system sets a default TTL value for outgoing packets, which can be used to identify the operating system.

Select a packet with a TTL value that is different from the others. Right-click on the packet and select "Follow > TCP stream" from the context menu.

The TCP stream window will show the packets that belong to the selected session. The source and destination IP addresses and port numbers will be displayed at the top of the window.

To view the data sent and received during the session, click on the "ASCII" or "Hex dump" buttons at the bottom of the window.

Repeat the process for other packets with different TTL values to identify more TCP sessions.

By following these steps, you can use the TTL field in the IP header to identify TCP sessions in Wireshark.
<img src="sessions.png" alt="Finding Session" >
___
<h3>Finding Open Ports</h3>
Here are the steps to find the open ports in Wireshark using the "Statistics" menu:

Open Wireshark and load the captured network traffic file.

Go to the "Statistics" menu and select "Conversations."

In the "Conversations" window, select the "TCP" tab.

In the TCP tab, you will see a list of all the TCP conversations that took place during the captured network traffic.

Click on the "Service" column to sort the list based on the services used during these conversations.

Look for the services that are using a high number of ports. These are the services that are likely to have multiple open ports.

Select the service you want to investigate and click on the "Follow" button to view the details of the selected conversation.

In the "Follow TCP Stream" window, you will see the details of the conversation, including the ports that were used.

Note down the ports that were used for the selected service, as these are the open ports for that service.

Repeat the above steps for each service you want to investigate.

That's it! By following these steps, you can easily find the open ports in Wireshark by going to "Statistics" -> "Conversations" -> "TCP list".
<img src="Screenshot (14).png" alt="Open Ports" >
