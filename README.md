
 ZIP Password Cracker with John the Ripper

A simple tool cracking for ZIP files using John the Ripper.

Disclaimer: For educational and authorized testing purposes only.

Quick Start

1.  Install JohnTheRipper
    
    [+] sudo apt install john    

2.  Run the Script
    Place your ZIP file (e.g., `secret.zip`) in the directory and run:
    
    [+] zip2john secret.zip > hashes.txt
    
    This uses the built-in `rockyou.txt` wordlist.

Usage

Modes:
- (default): Uses `rockyou.txt`.
- `wordlist <path/to/list.txt>`: Uses a custom wordlist.
- `single`: Uses single crack mode.
- `incremental`: Pure brute-force (very slow).


john hashes.txt [mode] [wordlist]

[+] john --wordlist="/usr/share/wordlists/rockyou.txt hashes.txt 

output :
``
Using default input encoding: UTF-8
Loaded 1 password hash (PKZIP [32/64])
Will run 8 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
marfin12345      (secret.zip/data.txt)     
1g 0:00:00:00 DONE (2026-01-13 21:30) 16.66g/s 273066p/s 273066c/s 273066C/s 123456..cutypie
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 
``
The password was successfully brute-forced and the password was found to be "marfin12345"

 How It Works
The  `john` automates two main steps:
1.  Extracts Hash: Uses `zip2john` to get the password hash from the ZIP file.
2.  Cracks Hash: Runs `john` with the specified mode to find the password.

 Requirements

- Linux (Debian/Ubuntu/Kali)
- John the Ripper
- zip2john
