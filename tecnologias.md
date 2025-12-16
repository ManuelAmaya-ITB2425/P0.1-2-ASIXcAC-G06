**# 🚀 Estudio de tecnologías disponibles

---

## 🧩 Contexto del proyecto

El proyecto se basara en el despliegue de una applicación web, esto lo haremos en un entorno servidor Linux. Al principio trabajaremos con una maquina virtual, para evitar costes a la hora de lanzar instancias en AWS, para luego una vez tener la base y todo configurado migrarlo a AWS.

La selección de tecnologias la haremos teniendo encuenta cuatro cosas:

- **El rendimiento** asegurándonos de que todo lo que vayamos a configurar y lanzar funcione de manera eficaz sin ningún tipo de problema, ya sea de compatibilidad, ajustes o versiones. Que el software se gestione bien y cargue sin usar muchos recursos ni peticiones.
- **Mantenimiento**, queremos que todo lo que se configure se pueda editar, actualizar o mantener de una manera fácil y sencilla, sin necesidad de tener que acceder a mil directorios y sin dependencias complejas.
- **Uso real en entornos profesionales**, queremos que lo que configuremos nos sirva para más tarde, a la hora de trabajar, para poder tener una base sólida de algo real, tecnologías que se usen en empresas reales y con soporte.
- **Infraestructuras Cloud**. Finalmente queremos que haya compatibilidad, que todo lo que configuramos funcione igual en una Máquina Virtual Local que en AWS, permitiendo pasar datos y configuración sin tener que rehacer arquitectura ni configuraciones.

  
---

## 🌐 Servidor web: NGINX vs Apache
Apache ha sido durante años el servidor web más utilizado. Es flexible, muy documentado y fácil de configurar, pero su modelo basado en procesos consume más recursos y escala peor cuando hay muchas conexiones simultáneas.

NGINX utiliza un modelo asíncrono orientado a eventos, lo que le permite gestionar un gran número de conexiones con menor consumo de CPU y memoria. Es el estándar de facto en entornos cloud y arquitecturas modernas.

✅ **Decisión:** Se elige **NGINX** por rendimiento, eficiencia y alineación con AWS.

---

## ⚙️ Ejecución de PHP: PHP-FPM
PHP-FPM permite ejecutar PHP como un servicio independiente del servidor web. Esto mejora el rendimiento, facilita la configuración y aumenta la seguridad al separar responsabilidades.

Es la solución recomendada cuando se utiliza NGINX y permite escalar el servicio de forma más sencilla en el futuro.

✅ **Decisión:** Se utiliza **PHP-FPM** como gestor de procesos PHP.

---

## 🗄️ Sistema gestor de bases de datos: MySQL
MySQL es un sistema gestor de bases de datos relacional muy extendido en aplicaciones web. Es estable, eficiente y totalmente compatible con Linux, Docker y servicios gestionados en AWS.

Para el alcance del proyecto no se requiere una base de datos más compleja, por lo que MySQL resulta una opción adecuada y realista.

✅ **Decisión:** Se utiliza **MySQL** como base de datos relacional.

---

## 📦 Contenerización: Docker
Docker permite encapsular servicios y dependencias en contenedores, facilitando la portabilidad del entorno y la coherencia entre desarrollo y producción.

Aunque no es imprescindible en la fase inicial, su uso aporta buenas prácticas profesionales y simplifica la futura migración a AWS.

✅ **Decisión:** Docker se considera una tecnología complementaria y recomendable.

---

## 🧱 Stack tecnológico final
El stack tecnológico seleccionado para el proyecto es:

- 🌐 **NGINX** como servidor web
- ⚙️ **PHP-FPM** para la ejecución de PHP
- 🗄️ **MySQL** como sistema gestor de bases de datos
- 📦 **Docker** como herramienta de contenerización (opcional)

Este conjunto de tecnologías es coherente, eficiente y alineado con entornos profesionales y cloud.
**
