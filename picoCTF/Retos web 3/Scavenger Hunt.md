## Objetivo
There is some interesting information hidden around this site [http://mercury.picoctf.net:55079/](http://mercury.picoctf.net:55079/). Can you find it?

**Hints** You should have enough hints to find the files, don't run a brute forcer.
## Solución
Revisamos el código fuente y ahí encontramos la primera parte de la bandera.
![[Pasted image 20240926083911.png]]
En la hoja de estilos encontramos la segunda parte:
![[Pasted image 20240926084005.png]]
En el archivo robots.txt encontramos la tercera parte:
![[Pasted image 20240926084111.png]]
En .htaccess encontramos la cuarta parte:
![[Pasted image 20240926084310.png]]
En el archivo .DS_Store encontramos la última parte de la bandera:
![[Pasted image 20240926084520.png]]
## Referencias
[.DS_Store](https://es.wikipedia.org/wiki/.DS_Store)