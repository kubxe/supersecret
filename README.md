# supersecret
Explorer practice
Here’s a clear breakdown and guide in English for each part of Ticket C tasks:

⸻

1. Vulnerability Scan on Metasploitable2 (Easy, 5 points)
	•	Use Nessus or OpenVAS to scan the Metasploitable2 VM.
	•	Identify at least one confirmed critical vulnerability.
	•	Provide its CVE code and name.
	•	Export the scan report excerpt as PDF or screenshot.

⸻

2. Find Recently Modified Files in Linux (Easy, 5 points)
	•	Use stat and find to check files modified in the last few minutes.
	•	Example command:

find /path/to/search -type f -mmin -5 -exec stat -c "%n %y" {} \;

	•	List at least 3 files with full paths and modification timestamps.

⸻

3. Find Passwords with “123” and Length < 8 in rockyou.txt.gz (Easy, 5 points)
	•	Use zcat and grep to filter passwords:

zcat rockyou.txt.gz | grep "123" | awk 'length($0) < 8' | head -n 3

	•	Present at least 3 matching password examples.

⸻

4. SSH Login Brute-Force with Hydra (Medium, 10 points)
	•	Command example:

hydra -l admin -P /usr/share/wordlists/rockyou.txt 192.168.56.101 ssh

	•	If successful login occurs, note the username, password, and provide a screenshot of the login success.

⸻

5. File System Changes Analysis Using comm and diff (Medium, 10 points)
	•	Take snapshots of file lists before and after malware execution:

find /target/directory -type f | sort > before.txt
# Run malware in sandbox
find /target/directory -type f | sort > after.txt
comm -13 before.txt after.txt  # Lists new files
diff before.txt after.txt      # Shows all differences

	•	Identify and report at least 2 new or modified files with names and directories.

⸻

6. Analyze AIM Messaging Traffic on Port 443 from .pcap (Medium, 10 points)
	•	Open .pcap in Wireshark.
	•	Filter for traffic on port 443.
	•	Extract server IP used for AIM.
	•	Use whois or ipinfo.io to check IP ownership.
	•	Confirm if the IP belongs to AOL, and include proof from lookup.

⸻

7. Identify TCP SYN Packets Without Response in .pcap (Hard, 20 points)
	•	Filter in Wireshark for TCP SYN packets without ACK response.
	•	Extract IPs initiating these connections.
	•	Use geoiplookup, whois, or ipinfo to find geolocation of IPs.
	•	Explain this traffic pattern as likely a SYN Flood attack and describe potential risks.

⸻

If you want, I can help you with commands, example outputs, or analysis for any specific step!