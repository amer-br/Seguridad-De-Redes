## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

## Solución
File > ExportObjects > HTTP > guardar la imagen en una carpeta

```bash
                                                                            
┌──(kali㉿kali)-[~/picoCTFretos/forensic/WebNet1]
└─$ strings vulture.jpg | grep pico
picoCTF{honey.roasted.peanuts}

```

