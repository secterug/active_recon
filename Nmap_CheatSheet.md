
## Nmap Cheat Sheet

### Basic Scanning Techniques
* Scan a single target
	* `nmap [target]`
* Scan multiple targets
	* `nmap [target1,target2,etc]`
* Scan a list of targets
	* `nmap -iL [list.txt]`
* Scan a range of hosts
	* `nmap [range of IP addresses]
* Scan an entire subnet	
	* `nmap [IP address/cdir]`
* Scan random hosts 
	* `nmap -iR [number]`
* Excluding targets from a scan	
	* `nmap [targets] –exclude [targets]`
* Excluding targets using a list
	* `nmap [targets] –excludefile [list.txt]`
* Perform an aggressive scan
	* `nmap -A [target]`
* Scan an IPv6 target
	* `nmap -6 [target]`

### Discovery Options
* Perform a ping scan only
	* `nmap -sP [target]`
* Don’t ping
	* `nmap -PN [target]`
* TCP SYN Ping	
	* `nmap -PS [target]`
* TCP ACK ping
	* `nmap -PA [target]`
* UDP ping
	* `nmap -PU [target]`
* SCTP Init Ping
	* `nmap -PY [target]`
* ICMP echo ping
	* `nmap -PE [target]`
* ICMP Timestamp ping
	* `nmap -PP [target]`
* ICMP address mask ping
	* `nmap -PM [target]`
* IP protocol ping
	* `nmap -PO [target]
* ARP ping
	* `nmap -PR [target]`
* Traceroute
	* `nmap –traceroute [target]`
* Force reverse DNS resolution
	* `nmap -R [target]`
* Disable reverse DNS resolution
	* `nmap -n [target]`
* Alternative DNS lookup
	* `nmap –system-dns [target]`
* Manually specify DNS servers
	* `nmap –dns-servers [servers] [target]`
* Create a host list
	* `nmap -sL [targets]`

### Advanced Scanning Options
* TCP SYN Scan
	* `nmap -sS [target]`
* TCP connect scan
	* `nmap -sT [target]`
* UDP scan
	* `nmap -sU [target]`
* TCP Null scan
	* `nmap -sN [target]`
* TCP Fin scan
	* `nmap -sF [target]`
* Xmas scan
	* `nmap -sX [target]`
* TCP ACK scan
	* `nmap -sA [target]`
* Custom TCP scan
	* `nmap –scanflags [flags] [target]`
* IP protocol scan
	* `nmap -sO [target]`
* Send Raw Ethernet packets
	* `nmap –send-eth [target]`
* Send IP packets
	* `nmap –send-ip [target]`

### Port Scanning Options
* Perform a fast scan
	* `nmap -F [target]`
* Scan specific ports
	* `nmap -p [ports] [target]`
* Scan ports by name
	* `nmap -p [port name] [target]`
* Scan ports by protocol
	* `nmap -sU -sT -p U:[ports],T:[ports] [target]`
* Scan all ports
	* `nmap -p “*” [target]`
* Scan top ports
	* `nmap –top-ports [number] [target]
* Perform a sequential port scan
	* `nmap -r [target]`

### Version Detection
* Operating system detection
	* `nmap -O [target]`
* Submit TCP/IP Fingerprints
	* `http://www.nmap.org/submit/`
* Attempt to guess an unknown
	* `nmap -O –osscan-guess [target]`
* Service version detection
	* `nmap -sV [target]`
* Troubleshooting version scans
	* `nmap -sV –version-trace [target]`
* Perform a RPC scan
	* `nmap -sR [target]`

### Timing Options
* Timing Templates
	* `nmap -T [0-5] [target]`
* Set the packet TTL
	* `nmap –ttl [time] [target]`
* Minimum of parallel connections
	* `nmap –min-parallelism [number] [target]`
* Maximum of parallel connection
	* `nmap –max-parallelism [number] [target]`
* Minimum host group size
	* `nmap –min-hostgroup [number] [targets]`
* Maximum host group size
	* `nmap –max-hostgroup [number] [targets]`
* Maximum RTT timeout
	* `nmap –initial-rtt-timeout [time] [target]`
* Initial RTT timeout
	* `nmap –max-rtt-timeout [TTL] [target]`
* Maximum retries
	* `nmap –max-retries [number] [target]`
* Host timeout
	* `nmap –host-timeout [time] [target]`
* Minimum Scan delay
	* `nmap –scan-delay [time] [target]`
* Maximum scan delay
	* `nmap –max-scan-delay [time] [target]`
* Minimum packet rate
	* `nmap –min-rate [number] [target]`
* Maximum packet rate
	* `nmap –max-rate [number] [target]`
* Defeat reset rate limits
	* `nmap –defeat-rst-ratelimit [target]`

### Firewall Evasion Techniques
* Fragment packets
	* `nmap -f [target]`
* Specify a specific MTU
	* `nmap –mtu [MTU] [target]`
* Use a decoy
	* `nmap -D RND: [number] [target]`
* Idle zombie scan
	* `nmap -sI [zombie] [target]`
* Manually specify a source port
	* `nmap –source-port [port] [target]`
* Append random data
	* `nmap –data-length [size] [target]`
* Randomize target scan order
	* `nmap –randomize-hosts [target]`
* Spoof MAC Address
	* `nmap –spoof-mac [MAC|0|vendor] [target]`
* Send bad checksums
	* `nmap –badsum [target]`

### Output Options
* Save output to a text file
	* `nmap -oN [scan.txt] [target]`
* Save output to a xml file
	* `nmap -oX [scan.xml] [target]`
* Grepable output
	* `nmap -oG [scan.txt] [target]`
* Output all supported file types
	* `nmap -oA [path/filename] [target]`
* Periodically display statistics
	* `nmap –stats-every [time] [target]`
* 133t output
	* `nmap -oS [scan.txt] [target]`

### Troubleshooting and debugging
* Help
	* `nmap -h`
* Display Nmap version
	* `nmap -V`
* Verbose output
	* `nmap -v [target]`
* Debugging
	* `nmap -d [target]`
* Display port state reason
	* `nmap –reason [target]`
* Only display open ports
	* `nmap –open [target]`
* Trace packets
	* `nmap –packet-trace [target]`
* Display host networking
	* `nmap –iflist`
* Specify a network interface
	* `nmap -e [interface] [target]`

### Nmap Scripting Engine
* Execute individual scripts
	* `nmap –script [script.nse] [target]`
* Execute multiple scripts
	* `nmap –script [expression] [target]`
* Script categories
	* `all, auth, default, discovery, external, intrusive, malware, safe, vuln`
* Execute scripts by category
	* `nmap –script [category] [target]`
* Execute multiple scripts categories
	* `nmap –script [category1,category2, etc]`
* Troubleshoot scripts
	* `nmap –script [script] –script-trace [target]`
* Update the script database
	* `nmap –script-updatedb`

### Ndiff
* Comparison using Ndiff
	* `ndiff [scan1.xml] [scan2.xml]`
* Ndiff verbose mode
	* `ndiff -v [scan1.xml] [scan2.xml]`
* XML output mode
	* `ndiff –xml [scan1.xm] [scan2.xml]`

### Links
* [Man Pages - http://nmap.org/book/man.html](http://nmap.org/book/man.html
* [Nmap Scripting Engine - http://nmap.org/book/nse.html](http://nmap.org/book/nse.html)
* [Nmap Scripting Engine list of current scripts - http://nmap.org/nsedoc/index.html](http://nmap.org/nsedoc/index.html)
* [Nmap Scripting Engine Documentation - http://nmap.org/book/nse.html](http://nmap.org/nsedoc/index.html)
* [Common Nmap Comman Examples - http://hackertarget.com/nmap-cheatsheet-a-quick-reference-guide/](http://nmap.org/nsedoc/index.html)
* [30 Nmap Command Examples - http://www.cyberciti.biz/networking/nmap-command-examples-tutorials/](http://www.cyberciti.biz/networking/nmap-command-examples-tutorials/)


```
Handy Examples:
Nmap Basics:

Scan a single target
	nmap [IP]

Scan multiple IPs
	nmap [IP1,IP2,IP3…]

Scan a list
	nmap -iL [list.txt]

Scan a range of hosts
	nmap [10.1.1.1-10.1.1.200]

Scan an entire subnet
	nmap [IP address/cdir]

Excluding targets from a scan
	nmap [IP] –exclude [IP]

Excluding targets using a list
	nmap [IPs] –excludefile [list.txt]

Create a list of hosts scanned
  	nmap -sL [IPs

     Evasion
Fragment packets
	nmap -f [IP]

Specify a specific MTU
	nmap –mtu [MTU] [IP]

Append random data
	nmap –data-length [size] [IP]

Spoof MAC Address
	nmap –spoof-mac [MAC|0|vendor] [IP]

Send bad checksums
	nmap –badsum [IP]

## Output
Save output to a text file
	nmap -oN [scan.txt] [IP]

Save output to a xml file
	nmap -oX [scan.xml] [IP]

Grepable output
	nmap -oG [scan.txt] [IP]

Output all supported file types
	nmap -oA [path/filename] [IP

## Comparing Scan Results
Comparison using Ndiff 
	ndiff [scan1.xml] [scan2.xml]

Ndiff verbose mode
	ndiff -v [scan1.xml] [scan2.xml]

XML output mode 
	ndiff –xml [scan1.xm] [scan2.xml]]

Nmap Scripting Engine

Execute individual NSE scripts
	nmap –script [script.nse] [IP]

Execute multiple NSE scripts
	nmap –script [script1.nse,script2.nse…] [IP]

Execute NSE scripts by category
	nmap –script [cat] [target]

Execute multiple NSE script categories
	nmap –script [auth, default…] [IP]

NSE Script categories:
all 
auth
default
discovery
external
intrusive
malware
safe

## Putting it together
# Nmap verbose scan, runs syn stealth, T4 timing (should be ok on LAN), OS and service version info, traceroute and scripts against services
nmap -v -sS -A -T4 target

# As above but scans all TCP ports (takes a lot longer)
nmap -v -sS -p- -A -T4 target

# As above but scans all TCP ports and UDP scan (takes even longer)
nmap -v -sU -sS -p- -A -T4 target

# Search nmap scripts for keywords
ls /usr/share/nmap/scripts/* | grep ftp

# Nmap script to scan for vulnerable SMB servers - WARNING: unsafe=1 may cause knockover
nmap -v -p 445 --script=smb-check-vulns --script-args=unsafe=1 target

## run three Nmap scans to identify accessible hosts
nmap –T4 –Pn –n –sS –F –oG tcp.gnmap 192.168.0.0/24
nmap –T4 –Pn –n –sY –F –oG sctp.gnmap 192.168.0.0/24
nmap –T4 –Pn –n –sU –p53,69,111,123,137,161,500,514,520 -oG  udp.gnmap 192.168.0.0/24

## use grep and awk to generate a refined list of targets
grep open *.gnmap | awk '{print $2}' | sort | uniq > targets.txt

## feed this list into four subsequent scans
1. A fast TCP scan of common services
nmap -T4 -Pn -open -sS -A -oA tcp_fast -iL targets.txt

2. A TCP scan of all ports (plus fingerprinting and testing via default NSE scripts)
nmap -T4 -Pn -open -sSVC -A –p0-65535 -oA tcp_full -iL targets.txt

3. An SCTP scan of all ports
nmap -T4 -Pn -open -sY –p0-65535 -oA sctp -iL targets.txt

4. A UDP scan of common services
nmap -T3 -Pn -open –sU -oA udp -iL targets.txt
