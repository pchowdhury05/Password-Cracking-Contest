**Cracked Passwords**:
jackbear:speed-order

barneybear:dha4

yogibear:Curtium

cozybear:500768

carebear:rd2tgq7k

papabear:anthony

grizzlybear:147852369

pandabear:Password21&
 
**Methodologies**:
I initially started cracking passwords by using John the Ripper and the Seclist. Through this combination, I successfully cracked 3 passwords using wordlists such as: worst-passwords.txt, Lizard-Squad.txt, and common_corporate_passwords.txt. After exhausting the Seclist with John the Ripper and obtaining no further results, I moved on to using Hashcat, which gave me the most results. After utilizing Hashcat, I cracked 5 passwords using wordlists such as: openwall.net-all.txt (2 cracked passwords), darkc0de.txt, and xato-net-10-million-passwords.txt (2 cracked passwords).
These are the command prompts I used for each hash:  
jackbear:speed-order  — hashcat -m 500 -a 0 -O -w 3 md_hashes.txt openwall.net-all.txt
barneybear:dha4 — hashcat -m 500 -a 0 -O -w 3 md_hashes.txt darkc0de.txt -o cracked_passwords.txt
yogibear:Curtium — hashcat -m 500 -a 0 -O -w 3 md_hashes.txt openwall.net-all.txt
cozybear:500768 — hashcat -m 500 -a 0 -O -w 3 md_hashes.txt xato-net-10-million-passwords.txt
carebear:rd2tgq7k — hashcat -m 500 -a 0 -O -w 3 md_hashes.txt xato-net-10-million-passwords.txt
papabear:anthony  — john --wordlist=500-worst-passwords.txt crackme-spring2024.txt --format=sha512crypt
grizzlybear:147852369 — john --wordlist=Lizard-Squad.txt crackme-spring2024.txt --format=sha512crypt
pandabear:Password21& — john --wordlist=common_corporate_passwords.txt crackme-spring2024.txt --format=sha512crypt
 
Lastly, after cracking these passwords I made sure to check to see if they were correct by using a openSSL. I used a command prompt like this: openssl passwd -1 -salt BGVAnquQ speed-order. All the results came out true.
