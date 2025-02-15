In this project, I utilized various techniques to exploit vulnerabilities and gain access to a target machine, eventually retrieving a flag. Here’s how the process unfolded:

Setting up the Attacker Server: I configured my Kali Linux machine as the attacker server with the IP address 10.10.1.231. I began by executing commands in the terminal to carry out different tasks.

Phishing Attack: I initiated a phishing campaign by sending emails to addresses listed in the emails.txt file. Using the sendemail tool, I mass-mailed emails with an attached malicious file, shell.exe, which I had generated earlier using msfvenom. The file was designed to trigger a reverse shell back to my server, allowing me to gain remote access.

Gaining Remote Access: After the targets opened the phishing emails and executed the malicious file, I used nc (netcat) to listen on port 443 on my server and establish a connection. This granted me access to the victim’s system, which was running Windows.

Elevating Privileges: I gained access to the user wrohit, who was part of the Administrators group. This provided me with elevated privileges, enabling me to load Mimikatz and dump password hashes from the Windows registry.

Mimikatz for Password Extraction: I downloaded Mimikatz on the victim machine using curl, then executed mimikatz.exe "token::elevate" "lsadump::sam" to extract the password hash for the user wrohit. I cracked the hash and successfully retrieved the password.

Finding the hMailServer Password: I located the password for the hMailServer Admin Dashboard within the hMailServer.INI configuration file, which was stored in C:\Program Files (x86)\hMailServer\Bin\. The file contained the hashed password for the administrator panel.

Flag Retrieval: Finally, I discovered a flag file on the user wrohit’s desktop. The file flag.txt contained the flag in the format THM{l1v1n_7h3_br1ck_l1f3}.
