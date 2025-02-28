I conducted research as part of a CTF challenge related to exploiting vulnerabilities and interacting with an MQTT broker. Initially, I attempted to use RustScan to scan the network but encountered errors during installation due to GPG key issues. I then started working with MQTT, sending commands via mosquitto_pub and decoding responses using base64. During the process, I discovered a backdoor that allowed sending commands in JSON format encoded in base64. I used the SYS command to retrieve system information and the CMD command to execute commands on the remote machine. Eventually, I found a file named flag.txt, sent the cat flag.txt command via MQTT, and obtained the flag: flag{18d44fc0707ac8dc8be45bb83db54013}. Thus, I successfully exploited the vulnerability, used MQTT to control the system, and gained access to confidential information, demonstrating my skills in penetration testing and cybersecurity.
