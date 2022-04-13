### Discovery

1. Search subnet for target computers:
   
`nmap 192.168.1.1/24`

![Nmap Subnet Scan](images_part1/nmap_subnet_scan.png)

2. Probe 192.168.1.105

`nmap -sC 192.168.1.105`

![Scan of 192.168.1.105](images_part1/nmap_scan_target_105.png)

3. Dirb 192.168.1.105

`dirb http://192.168.1.105`

![Dirb of 192.168.1.105](images_part1/dirb_target_105.png)

4. Navigate through website.

![Company employees](images_part1/company_employees.png)

5. Under CEO's page - Info pointing to a Secret folder

![Secret Folder Clue](images_part1/secret_folder_clue.png)

6. Secret Folder Restricted Login

![Secret Folder Login](images_part1/secret_folder_login.png)

7. Login obtained using brute force via Hydra

`hydra -l ashton -P /usr/share/wordlists/rockyou.txt -s 80 -f -vV 192.168.1.105 http-get /company_folders/secret_folder`

![Password Found](images_part1/password_found.png)

8. Secret folder contents / instructions to access corporate server

![Secret Folder contents](images_part1/secret_folder_contents.png)

![Instructions to access corporate server](images_part1/corp_server_instructions.png)

9. Password crack on Ryan's account using CrackStation

![CrackStation - Ryan](images_part1/crack_station_ryan.png)

10. Create payload - MSF Venom

Source: https://infinitelogins.com/2020/01/25/msfvenom-reverse-shell-payload-cheatsheet/

![Payload Syntax Examples](images_part1/payload_syntax_examples.png)

![Payload Created](images_part1/payload_created.png)

11. Payload uploaded using default linux file manager

![Payload Uploaded 1](images_part1/payload_uploaded.png)

![Payload Uploaded 2](images_part1/payload_uploaded_2.png)

12. Setting up listener - Metasploit - multi/handler

![Setting Up Listener](images_part1/setting_up_listener.png)

13. Successful reverse Meterpreter shell

![Successful reverse shell](images_part1/successful_connection.png)

14. Navigating target file structure

![Target folder](images_part1/target_root_folder.png)

15. Located flag

![The Flag](images_part1/flag.png)
