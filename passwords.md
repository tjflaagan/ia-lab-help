# Passwords

## John the Ripper

1. Using an effective wordlist, like rockyou.txt, is useful.
2. By default, rockyou.txt is located at /usr/share/wordlists/rockyou.txt
3. You may have to unzip rockyou.txt.gz. To do so, enter the following input: 
	`sudo gunzip /usr/share/wordlists/rockyou.txt.gz`
4. Example of proper John the Ripper Input:
	`john <password file> --format=RAW-MD5 --wordlist=/usr/share/wordlists/rockyou.txt
	
## Useful hash identifiers/crackers

	1. [https://hashes.com/en/tools/hash_identifier] (https://hashes.com/en/tools/hash_identifier)
	2. [https://md5hashing.net/hash_type_checker] (https://md5hashing.net/hash_type_checker)
	3. [https://crackstation.net/] (https://crackstation.net/)


