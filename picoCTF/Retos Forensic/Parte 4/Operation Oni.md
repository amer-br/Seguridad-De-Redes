## Objetivo
Download this disk image, find the key and log into the remote machine. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

Additional details will be available after launching your challenge instance.

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/forensic/OperationOni]
└─$ fls -o 0000206848 disk.img 470 -r
r/r 2344:       .ash_history
d/d 3916:       .ssh
+ r/r 2345:     id_ed25519
+ r/r 2346:     id_ed25519.pub
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/OperationOni]
└─$ icat -o 0000206848 disk.img 2344 -r
ssh-keygen -t ed25519
ls .ssh/
halt
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/OperationOni]
└─$ icat -o 0000206848 disk.img 2345 -r
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/OperationOni]
└─$ icat -o 0000206848 disk.img 2345 -r > key_file
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/OperationOni]
└─$ chmod 600 key_file 
                                                                             
┌──(kali㉿kali)-[~/picoCTFretos/forensic/OperationOni]
└─$ ssh -i key_file -p 53263 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:53263 ([13.59.203.175]:53263)' can't be established.
ED25519 key fingerprint is SHA256:XBSvB1lk28EctsAVdKJtsl0A7C5bonqPrvHCYH8aEy4.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:53263' (ED25519) to the list of known hosts.
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat flag.txt 
picoCTF{k3y_5l3u7h_af277f77}ctf-player@challenge:~$
```
