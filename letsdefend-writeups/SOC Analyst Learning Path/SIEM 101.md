- A SIEM collects and interprets data then detects potential threats.
- You can use Gartner to see most successful SIEM solutions.
## Log Collection
- Logging is act of keeping a log.
- A log is a file that records events in a system, software, or communication between users.
- Logs are collected in two ways:
	- Log agents - Requires software. Can take action on logs before forwarding to target.
		- Automatic parsing, encryption, log integrity, etc.
		- Costly - computer resource usage increased.
		- i.e., Syslog (UDP [1024 bytes] /TCP [4096 bytes]), Splunk universal forwarder, ArcSight, Beats NXLog.
	- Agentless - No installation and update cost.
		- Username and password of log server required.
		- Limited capabilities.
		- Easier to prepare and manage.
		- Risk password being stolen.

#### Q1: What is the best method for those who do not want to manage agent software?
```
Agentless
```

#### Q2: “Universal Forwarder” is the agent software of which product?
```
Splunk
```

## Log Aggregation and Parsing
- Logs are first sent to log aggregator.
	- Can edit - i.e., Send only desired parts to target.
### Aggregator EPS
- EPS stands for events per second.
	- Events divided by period of seconds.
	- As value increases, aggregator and storage area should also increase.
- Can scale aggregator (add another one).
- Parsing (interpreting), filtering, enrichment (add data).
	- Enrichment examples: Geolocation, DNS, add/remove.

#### Q1: Which one is not the skill of a log aggregator?  
-filtering  
-parsing  
-analysis  
-enrichment
```
analysis
```

#### Q2: What is the EPS of a SIEM system that receives 150000 logs per minute?
```
2500
```
150000 logs / 60 seconds = 2500 logs/second

## Log Storage
- Common mistakes in SIEM structures is storage size.
- High storage and high speed of accessing data is important.
- WORM (write once read many) based technologies may be more suitable for SIEM.
	- Once information is written, it cannot be modified.

#### Q1: Is data update (change value, delete value etc) very important for SIEM data storage?  
  
Answer Format: Y/N
```
N
```
Reading data is more important for SIEM.

#### Q2: Which one is the most important for SIEM storage?  
  
-Speed  
-Features  
-Price
```
Speed
```
Speed can be a difference maker between resolving security incidents or not.

## Alerting
- Alerts should be optimized such that they are not triggered in large numbers.
- Some ways to create alerts:
	- Search stored data.
	- Create alarms while taking logs.
### Blacklist
- Used for undesirable situations
- Alert can be generated for prohibited processes or banned IPs.
### Whitelist 
- Used for desirable situations.
- Generate alert if communication made with IP different from pre-defined list.
- Needs to be constantly updated.
### Long Tail Log Analysis
- Assumes behaviours that occur constantly are normal.

#### Q1: I have 2 IP addresses that are certain to be malicious. I want to create an alert when these are accessed. Which method should I use?  
  
-whitelisting  
-blacklist  
-long tail
```
blacklist
```

#### Q2: "The whitelist method is not only very effective but also very easy to manage." Is that true or false?
```
false
```
False because whitelisting requires constant updates to stay relevant - making it harder than blacklisting to manage.

- An attacker can use a command like `echo 1 >> mimikatz.exe` to bypass hash blacklist.
	- This command appends the character string `1` to `mimikatz.exe`.
