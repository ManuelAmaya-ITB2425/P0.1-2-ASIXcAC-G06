# pruebaphp.md

Una vez finalizada la instalación y la configuración, se realizan distintas pruebas para comprobar que **PHP-FPM funciona correctamente** y que la comunicación con el servidor web se realiza mediante **socket UNIX**, tal y como se ha configurado.

🔍 **Verificación del socket UNIX y permisos**  
Se comprueba que el socket UNIX generado por PHP-FPM existe y que tiene los permisos adecuados. Este paso confirma que el servicio ha arrancado correctamente y que el servidor web puede acceder al socket sin problemas de permisos.

*Comando utilizado:*  
<span style="color:#1f6feb"><i>ls -l /run/php-fpm/www.sock</i></span>

![](media/c15permisos.png)

📡 **Comprobación de escucha del socket**  
Se verifica que PHP-FPM está escuchando activamente en el socket UNIX. Esto confirma que el gestor de procesos está operativo y preparado para recibir peticiones desde el servidor web.

*Comando utilizado:*  
<span style="color:#1f6feb"><i>ss -xl | grep php-fpm</i></span>

![](media/c13unix.png)

🧪 **Creación de un archivo PHP de prueba**  
Se crea un archivo PHP sencillo para validar la ejecución real de código PHP a través de PHP-FPM. Este archivo se ubica en el directorio raíz del servidor web.

*Ruta del archivo:*  
<span style="color:#1f6feb"><i>/usr/share/nginx/html/test.php</i></span>

*Contenido del archivo:*  
```php
<?php echo "PHP-FPM OK\n"; ?>

🔐 **Ajuste de permisos del archivo**  
Se ajustan los permisos del archivo para que pertenezca al usuario `nginx`, evitando problemas de acceso y manteniendo un modelo de permisos coherente entre el servidor web y PHP-FPM.

Comando utilizado:  
<span style="color:#1f6feb"><i>sudo chown nginx:nginx /usr/share/nginx/html/test.php</i></span>

---

🌐 **Prueba final de ejecución**  
Finalmente se accede al archivo PHP desde local para comprobar que el código se ejecuta correctamente y que la respuesta es generada por PHP-FPM.

Comando utilizado:  
<span style="color:#1f6feb"><i>curl http://localhost/test.php</i></span>
