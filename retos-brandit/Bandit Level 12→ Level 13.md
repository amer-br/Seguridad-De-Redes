## Objetivo
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)
## Datos de acceso al nivel
bandit12
Contraseña: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
## Solución
#### Opción 1
```bash
bandit12@bandit:~$ mkdir /tmp/abdr
bandit12@bandit:~$ xxd -r data.txt > /tmp/abdr/data
bandit12@bandit:~$ cd /tmp/abdr/
bandit12@bandit:/tmp/abdr$ ls
data
bandit12@bandit:/tmp/abdr$ cat data
4�44ڞ������QC&�4Ѡ4␦b4��hh4d�h�4�h␦4�hç�␦v=o������������}����߰8l��m@�␦���4��M4=C@�
@�!�hɠP�4␦hh��d�a��A%Ջ���y�1�Ǆ����3�(���J�'O�!��,&3`��э`鱉J�:�a���i�E�d&��r�Q��qt]�lFwK�b]y�J�P�ဃ���o�\ՋBdb\��j���+>M*�O�l�i�͵��!Ģ:�e��*
                d�G�hH�_Xܟ���ڬ=V��A�Q(�G`'b���t�:�U��[��"2�>���M�^�'�U�u��x.���9A8\�Qz��M��E��!K'
                                                                                                 ��?K:`S
(�qϐD�<�cJ�;us�@W
                 ���*�,̄)�5h�
w�3A���� >ՊJ�({2��H%i���ڏ-B7-�?h�       mJ�5!0�ul/���P�N�_��H�
D���bandit12@bandit:/tmp/abdr$ file data
data: gzip compressed data, was "data2.bin", last modified: Wed Jul 17 15:57:06 2024, max compression, from Unix, original size modulo 2^32 577
bandit12@bandit:/tmp/abdr$ mv data data.gz
bandit12@bandit:/tmp/abdr$ gzip -d data.gz
bandit12@bandit:/tmp/abdr$ file data
data: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/abdr$ mv data data.bz2
bandit12@bandit:/tmp/abdr$ bzip2 -d data.bz2
bandit12@bandit:/tmp/abdr$ file data
data: gzip compressed data, was "data4.bin", last modified: Wed Jul 17 15:57:06 2024, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/abdr$ mv data data.gz
bandit12@bandit:/tmp/abdr$ gzip -d data.gz
bandit12@bandit:/tmp/abdr$ file data
data: POSIX tar archive (GNU)
bandit12@bandit:/tmp/abdr$ mv data data.tar
bandit12@bandit:/tmp/abdr$ tar xf data.tar
bandit12@bandit:/tmp/abdr$ ls
data5.bin  data.tar
bandit12@bandit:/tmp/abdr$ rm data.tar
bandit12@bandit:/tmp/abdr$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/abdr$ mv data5.bin data.tar
bandit12@bandit:/tmp/abdr$ ls
data.tar
bandit12@bandit:/tmp/abdr$ tar xf data.tar
bandit12@bandit:/tmp/abdr$ ls
data6.bin  data.tar
bandit12@bandit:/tmp/abdr$ rm data.tar
bandit12@bandit:/tmp/abdr$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/abdr$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/abdr$ la
data6.bz2
bandit12@bandit:/tmp/abdr$ ls
data6.bz2
bandit12@bandit:/tmp/abdr$ file data6.bz2
data6.bz2: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/abdr$ bzip2 -d data6.bz2
bandit12@bandit:/tmp/abdr$ ls
data6
bandit12@bandit:/tmp/abdr$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/abdr$ mv data6 data6.tar
bandit12@bandit:/tmp/abdr$ ls
data6.tar
bandit12@bandit:/tmp/abdr$ tar xf data6.tar
bandit12@bandit:/tmp/abdr$ ls
data6.tar  data8.bin
bandit12@bandit:/tmp/abdr$ rm data6.tar
bandit12@bandit:/tmp/abdr$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Wed Jul 17 15:57:06 2024, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/abdr$ mv data8.bin data8.gz
bandit12@bandit:/tmp/abdr$ gzip -d data8.gz
bandit12@bandit:/tmp/abdr$ ls
data8
bandit12@bandit:/tmp/abdr$ file data8
data8: ASCII text
bandit12@bandit:/tmp/abdr$ cat data8
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```
#### Opción 2
```bash
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```

## Notas adicionales
![[Pasted image 20240829211919.png]]
## Referencias
[Hex dump on Wikipedia](https://en.wikipedia.org/wiki/Hex_dump)