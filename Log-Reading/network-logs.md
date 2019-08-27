# Reading network logs


![](https://media.amazonwebservices.com/blog/2015/flow_see_a_stream_2.png)

2 123456789010 eni-abc123de 172.31.16.139 172.31.16.21 20641 22 6 20 4249 1418530010 1418530070 ACCEPT OK

2 123456789010 eni-abc123de 172.31.9.69 172.31.9.12 49761 3389 6 20 4249 1418530010 1418530070 REJECT OK

2 123456789010 eni-1a2b3c4d - - - - - - - 1431280876 1431280934 - NODATA

2 123456789010 eni-4b118871 - - - - - - - 1431280876 1431280934 - SKIPDATA

2 123456789010 eni-1235b8ca 203.0.113.12 172.31.16.139 0 0 1 4 336 1432917027 1432917142 ACCEPT OK

2 123456789010 eni-1235b8ca 172.31.16.139 203.0.113.12 0 0 1 4 336 1432917094 1432917142 REJECT OK

2 123456789010 eni-f41c42bf 2001:db8:1234:a100:8d6e:3477:df66:f105 2001:db8:1234:a102:3304:8879:34cf:4071 34892 22 6 54 8855 1477913708 1477913820 ACCEPT OK

### These are Amazon VPC Flow logs, which contain infomation about IP flows to virtual private clouds.

### Flow log format

#### `<version> <account-id> <interface-id> <srcaddr> <dstaddr> <srcport> <dstport> <protocol> <packets> <bytes> <start> <end> <action> <log-status>`




|**Field**   |**Description**     |
|------------|--------------------|
version | The VPC Flow Logs version.
account-id	| The AWS account ID for the flow log.
interface-id	| The ID of the network interface for which the traffic is recorded.
srcaddr | The source IPv4 or IPv6 address. The IPv4 address of the network interface is always its private IPv4 address.
dstaddr	| The destination IPv4 or IPv6 address. The IPv4 address of the network interface is always its private IPv4 address.
srcport | The source port of the traffic.
dstport	| The destination port of the traffic.
protocol	| The IANA protocol number of the traffic. For more information
packets	| The number of packets transferred during the capture window.
bytes | The number of bytes transferred during the capture window.
start | The time, in Unix seconds, of the start of the capture window.
end | The time, in Unix seconds, of the end of the capture window.
action |  The action associated with the traffic: ACCEPT: The recorded traffic was permitted by the security groups or network ACLs. REJECT: The recorded traffic was not permitted by the security groups or network ACLs.
log-status	| The logging status of the flow log: OK: Data is logging normally to the chosen destinations.  NODATA: There was no network traffic to or from the network interface during the capture window.  SKIPDATA: Some flow log records were skipped during the capture window. This may be because of an internal capacity constraint, or an internal error.
----

