## Objetivo


## Solución
```bash
──(kali㉿kali)-[~/picoCTFretos/forensic/wirwsharTwooTwooo]
└─$ tshark -r shark2.pcapng -T fields -e dns.qry.name -Y "dns.qry.name" | grep -oE "^[^.]*" | uniq | base64 -d

�:�G^��8tu
          ������8��\����U x�w��^�->y:����2�%���#�����M5���m�X���p�갔v/3�o�W��04òm�%�Ѐ��[ �1[_�Qj��u�����l]���;��fI���picoCT�m$���J�w�}g�Id|��Qx<����kOm������٭�M�'@:���(��`vE�-f2��6�p�8����K���?y m�$�SO���!*�b��H+
                                                          n�����% �xǑԂ&�:���E�+�i�1�<�Tqeb,+��▒��>�Q;�F�u▒2�2�$�GuDU��ח6ML��a����΂�g�ml
                                                          ZbI��i�93�ay�{�����l)kc�T�_��|�▒$��X�F$|�VM��f�V�+�Ql��RYF{dns_0J�Wd�Ku"���U�"[Kɱ▒XE��T�n��/t�tkX�*?F("?o5I��Vd�����3��v�"v����jw�Y�PkY��7`�V�'��h�4D
                                                     !B������O'k
��}#9�
      ���㋣TlρC�M�|��3����3I22\��әn���!v۵_���G/2>Cۃ▒|3�[�px�<ɹxU��▒�Jf�~�;IΛu���M�մ8�M�����(�\���c�3l�ҟʓ�_�k�-���'��NV;X�ƌS)4�8�����.�\��wa��r
                                               �ۺ�)�W����P��k�ʮ��4����ی���Ra
�ڑlBIZ�ꬊ�
_-�S�1l���&,�{��şvJNѝ?� �W]qr�k���ftw_de��1o��_▒2sb7�^KC���<�J`����<P�����'��:�t%��7��z�h�'���z�▒�~�A�,�4��8�H�      ���     C�ٻ|������]��[�PZ���,�a���hp7�k�{�+W��%>|�=��"�|�;t�-
                        &vj}�,.@GM&��ah�adbeefOQjꉱo��,{WE�$ԑ������
                                                                    �G�Խь�▒ �!-�,�-�"���y�G����cCR�|�844��ʉ��a�%B��F'ye'���e���D��Q�V�l����5a
                                                                ��#�V���t��Yv���W�"��0�ǒ�u���>�Ԩ�6���%�4��r�n������A��V�3}�>���|����k�K���b;�kSm��T�j.�����▒��u-�h�UG����Fh
                 �y��|d\7���t���+\���P
                                      ���z��
�w▒�%��#�������
               Y�Yn��1i錎y��ק�R��+(��/�rb���oJ�a��?U#�?潟���k�;��Ƨ�&�$ΐѲ�+��E��V|��SݠV�
       �w�O��M3�S��}


┌──(kali㉿kali)-[~/picoCTFretos/forensic/wirwsharTwooTwooo]
└─$ tshark -r shark2.pcapng -T fields -e dns.qry.name -Y "dns.qry.name && ip.dst == 18.217.1.57" | grep -oE "^[^.]*" | uniq | base64 -d

picoCTF{dns_3xf1l_ftw_deadbeef}    
```

