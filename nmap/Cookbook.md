**Scan network with wildcards**

	nmap 172.28.23.*

**Find live host in network**

	nmap -sP 172.28.23.*

**Scan specific port**
	
	nmap -p 61616 172.28.23.67

**Scan all ports**

	nmap -p- 172.28.23.67

**Only show open ports**

	nmap --open 172.28.23.67

**Detect OS**

	nmap -O ip

**Fastest way to scan**

	nmap -T5 iprange

**Detect port service and version**

	nmap -sV 172.28.23.67

**No port scan**

	nmap -sn 

**Generate xml Report and convert it to HTML**

    nmap -T4 -p 1-1000 -oX output.xml scanme.nmap.org
    xsltproc output.xml -o output.html

**Fast Discovery Scan**

	nmap -T5 -sL 172.28.23.*

	if -sL doens't work then

	nmap -T5 -F 172.28.23.*

**Faster Discovery Scan**

	nmap -p- --min-rate=1000 -sV <target_ip>
