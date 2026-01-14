# ZIP Password Cracker with John The Ripper

A simple tool cracking for ZIP files using John the Ripper.

<b> Disclaimer:</b> For educational and authorized testing purposes only.



Quick Start

1.  Install JohnTheRipper
    
    ``
    [+] sudo apt update
    ``

    ``
    [+] sudo apt install john
    ``

<img width="1350" height="419" alt="image" src="https://github.com/user-attachments/assets/5b592c50-88da-4484-a8f0-f600be609366" />


<img width="1347" height="258" alt="image" src="https://github.com/user-attachments/assets/eaa73a4e-3082-44d7-af69-35f3261b14d0" />
    

2.  Extract Hash file Zip
    Place your ZIP file (e.g., `secret.zip`) in the directory and run:
    
    ``[+] zip2john secret.zip > hashes.txt``

<img width="1351" height="385" alt="image" src="https://github.com/user-attachments/assets/88dce9ed-80fe-4d49-ad49-639b9d2fc342" />

    
3. Contents of the zip file

   ``[+] cat hashes.txt ``

   <img width="1359" height="171" alt="image" src="https://github.com/user-attachments/assets/64a2d479-e795-4a7e-b468-50402c626733" />


Usage

Modes:
- (default): Uses `rockyou.txt`.
- `wordlist <path/to/list.txt>`: Uses a custom wordlist.
- `single`: Uses single crack mode.
- `incremental`: Pure brute-force (very slow).


john hashes.txt [mode] [wordlist]

4. brute force zip password using wordlists mode

   
  `` [+] john --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt ``

<img width="1356" height="372" alt="image" src="https://github.com/user-attachments/assets/71b252bf-6d18-4af3-815b-1a17f19eca60" />



The password was successfully brute-forced and the password was found to be "marfin12345"

 How It Works
The  `john` automates two main steps:
1.  Extracts Hash: Uses `zip2john` to get the password hash from the ZIP file.
2.  Cracks Hash: Runs `john` with the specified mode to find the password.

 Requirements

- Linux (Debian/Ubuntu/Kali)
- John the Ripper
- zip2john
