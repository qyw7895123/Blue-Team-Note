# Incident Handling
![topology](https://w46tmw.by.files.1drv.com/y4mze41dOat8dCL1Wv2n5DBW0r3iX7OCuKeAQUGcnx8j9puz0ngKkCzJNfXIupQzRzmRybkyy_7M6Is8ocJqI2nSV5sqTnLtz4ELPM08k0hI_l7bKE3xqSum6REfIvCV-wqRuHX-EkvfFG689cQBao47F3rXY7FWM2FhkRhQgQ7iUDBornUvtZfZl1N9LxmLIbwINv59JXXFo7n01WXk5SAzg?width=924&height=470&cropmode=none)
### In this practical exercise we will gain familiarity with the incident handling process by examining artifacts of a potential network security incident and making recommendations to network administrators to limit exposure to future incidents.

### Scenario : Your network consists of a DMZ hosting basic services such as DNS, HTTP, FTP, and SSH, along with a user subnet (see topology above). Network traffic is being captured on your router's DMZ interface doing full packet capture on the traffic going into and out of your DMZ subnet, There is a firewall on your network's inbound link and the firewall rules are included in your file set (firewall rules.txt). you recently joined your organization;s incident handling team. One of the net work system administrators has noted anomalous traffic on the internal web server and has identified it as a "network event". You are on call and need to do an initial analysis of the data to determine whether the event should be classified as a "network incident". Assuming an incident has occurred, you will also be asked to make recommendations to your organization for mitigating this incident and for improving the security of your network.

1. What tools will you suse to analyze the network traffic and log files for this network event? List the tools that you will use during your investigation and update this list as you go through the lab.
    * Kali linux
    * Wireshark
    * 
2. What is the IP address of the host in the 172.16.2.0/24 subnet that accessed our DNS server? And what are the first three requests made from that host to our DNS server?
    * Open the incident_capture.pcap file with wireshark.
    * Filter the display by using "dns && ip.src==172.16.2.0/24"
    * We can see the result which is 172.16.2.58 accessed our DNS server.
    * And first three requests are shown in the screenshot.
    * ![wireshark](https://xi6tmw.by.files.1drv.com/y4mpiWe38nKF-F5TYG6XCtafv6rphi7TAGiHCYFjMrsdnrPBl4_9b_SS0v6B0_mdnNMHZxEK-iWJBT3qGWZ8ZVZ1AuRMmE8CTPlsza8lkm3obbvMj0PtS1pXu_l75kiHmMJQSC1kGkvGygUBV2CBoPUNrh8ODH_DCyqmAOrFFHUavzpS7brvyKqYnAOzMcNCLc1ehb3B84mSEU5lhFmIGN2BQ?width=1488&height=304&cropmode=none)
3. What information has the external host determined about our network that he/she might use during subsequent penetration attempts?
   * Now we can modify the display filter to "dns && ip.src==172.16.2.58 || ip.dst==172.16.2.58" in order to see all his requests and responses.
   * We can see the traffic No.49 he did a zone transfer on our DNS server to brute force our domain layout.
    ![wireshark49](https://xy6tmw.by.files.1drv.com/y4m0-Sl6suJn51tX4sPaGGNViOKs4GMpJsFz5JhgS6rKtP2zHc6k8xCiRJLJ5a5DVp-TJvhFKB901UUvo5D2nik3xTB2yBwjgEGC1C-ybhEFAj7frC4O6gVJJra6yvOE7soXra2xYZtDzqgvStT8eg8hAh9Yc__ba0VaFmjrH1mbNrn8yvJXzDY0cdGy_af7UH1vWCLHRBbbK3Bjl5zpDOWUA?width=1907&height=413&cropmode=none)
4. What is unusual about this interaction between an (external) Internet host and our DNS server?
   * 
5. Which hosts were scanned?
   * To determine this we can set our display filter to "ip.src==172.16.2.58 && ip.addr==10.10.4.0/24" to check all the queries he sends to the hosts in our subnet.
   * Click on statistics on toolbar then select conversations option. 
   * Then select the IPv4 section and check the limit to display filter option. Now we can see the hosts he scanned.
   * ![wire_scaned](https://xo6tmw.by.files.1drv.com/y4mW2Zsnj2gmgS6vyaW2_Y-eaDhwkcv8XAsTr1_et7Fu71WNUAbe_LkAdmyFm_Qvi0c3DrWAzAGHcGIKWQaKGNrqCx_38ZwyUxjtNppdPby4yAzDNUrSqRwfIKExPQFZpMqoWAWrisQGp4Vv-NuryVfA1ett6awkFdOjmP0Edq0G-FLB8WQElzZ23uHQ0sYt53nQBMGZ42hByigQVLJy8ZxnQ?width=1911&height=659&cropmode=none)
6. The attacker scanned the same group of ports on each server. Which ports did the attacker include in his/her scan of these hosts?
   * To do this we can change our display filter to "(tcp.flags==0x12) and not tcp.analysis.initial_rtt" to display only SYN ACK response. And we can see what ports he scans our hosts.
   * ![wire_synack](https://z46tmw.by.files.1drv.com/y4meyBzRMIG4weiMkGbSKNbnqh0IQe3KpRdILyCSLV--tzlFWLe2k_gZ8mXyXxrE61A7lq6OXObUNSQu8zM_Ns2tL2NAoVnP2xOYMg9EvDrZtk689tcltl4wNcBsXy8JuirErppMgr-mjyn-ftgaGcMlR1zbCqv6tKmG4bxBpUGw5wHUQqLDagCQA7gur2-tgtUS8Eb_DYyls3vSPfo-Y8Ygw?width=1918&height=230&cropmode=none)
7. Which ports did the attacker find open (which ports accepted connection attempts)? Hint: look for evidence of a complete TCP 3-way handshake.
  
                host   |   open ports   
                .1     |   22, 80, 443
                .12    |   21, 22, 80, 443
                .16    |   21, 22
                .251   |   53

8. What is wrong with our firewall rules that allowed these scans to get to our DMZ network? Hint: The firewall rules are provided in firewall rules.txt
   * ![defaultOpen](https://ai6tmw.by.files.1drv.com/y4mq22oxYab1yD8yQVa6oI_yT8z4VcdXwm2EcxTBE1o8kssY6iRT4larWEeP0qTqfMnmUdEnoXaijn8X90Ysm0MTHwv-PuyhymMzgcBz_ap9Qs9eoB9s0XMxI31RQZkRDePiJTelRw2sBGFR6qiaK5FkxNbBG4bXdZMrbcjMtrF-hhmK7EmV0SfdnSvPepVRtYjQKXPxdSucagI-decm_Kbww?width=929&height=253&cropmode=none)
   * The firewall rule just allows inbound traffic from any ip to our DMZ with all destination port. We should add rules specifically for each host to protect them from disposed.
9.  What did the attacker do during his/her anonymous login? Hint: look at both the ftp and ftp-data traffic (tcp ports 20 and 21)
    * 
10. What approach did the attacker take with the internal web server (what was he doing that could be considered malicious)? Give examples of the malicious behavior. Hint: Don't forget the log files?
11. What information was the attacker able to gain from the internal web  server that he could use in his continued attempts to compromise your network.
12. Which account does the attacker use to log in to the FTP server?
13. What password does the attacker use to log on to the FTP sever?
14. Where did the attacker get that password?
15. What files did the attacker attempt to GET from the FTP server?
16. Which files did they successfully GET?
17. The attacker placed some files on te FTP server. What are the names of the files the attacker fried to upload to the server?
18. Which files did he successfully upload?
19. Should any rules be immediately applied to prevent further malicious activity from the suspected attacker? If so, what should the new rules be?
20. Are there any other actions that you would recommend to system administrators to contain the current event? 

  
