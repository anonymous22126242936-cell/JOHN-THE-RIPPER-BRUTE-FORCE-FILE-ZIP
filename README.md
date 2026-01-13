
 ZIP Password Cracker with John the Ripper

A simple script to automate password cracking for ZIP files using John the Ripper.

Disclaimer: For educational and authorized testing purposes only.

Quick Start

1.  Clone and Install
    
    [+] sudo apt install john    

2.  Run the Script
    Place your ZIP file (e.g., `secret.zip`) in the directory and run:
    
    [+] zip2john secret.zip > hashes.txt
    
    This uses the built-in `rockyou.txt` wordlist.

Usage

john hashes.txt [mode] [wordlist]

Modes:
- (default): Uses `rockyou.txt`.
- `wordlist <path/to/list.txt>`: Uses a custom wordlist.
- `single`: Uses single crack mode.
- `incremental`: Pure brute-force (very slow).

 How It Works

The  `john` automates two main steps:
1.  Extracts Hash: Uses `zip2john` to get the password hash from the ZIP file.
2.  Cracks Hash: Runs `john` with the specified mode to find the password.

Results are saved in `hasil_crack.txt`.

 Requirements

- Linux (Debian/Ubuntu/Kali)
- John the Ripper
- zip2john
