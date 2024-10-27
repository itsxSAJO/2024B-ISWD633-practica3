## Esquema para el ejercicio
![Imagen](img/esquema-ejercicio3.PNG)

### Crear red net-wp

```
docker network create net-wp -d bridge
```
3.1.


En el esquema del ejercicio carpeta del contenedor (a) es: C:\Users\saidl\Desktop\EPN\6 Semestre\Construcción y Evolución de Software\Práctica 3\ejercicio3\db\mysql.env

Ruta carpeta host: C:\Users\saidl\Desktop\EPN\6 Semestre\Construcción y Evolución de Software\Práctica 3\ejercicio3\db

Para que la información de MySQL persista, es necesario montar un volumen en el directorio /var/lib/mysql, que es donde MySQL almacena sus datos en el contenedor.

### ¿Qué contiene la carpeta db del host?

3.2

La carpeta db contiene un archivo llamado mysql.env con el siguiente contenido:

```
MYSQL_ROOT_PASSWORD=root
MYSQL_DATABASE=mysql
MYSQL_USER=said
MYSQL_PASSWORD=root
```

Estas son variables de entorno para configurar el- contenedor MySQL, las cuales definen la contraseña del usuario root, el nombre de una base de datos, un usuario adicional, y su contraseña.


### Crear un contenedor con la imagen mysql:8  en la red net-wp, configurar las variables de entorno: MYSQL_ROOT_PASSWORD, MYSQL_DATABASE, MYSQL_USER y MYSQL_PASSWORD

```
docker run -d --name mi_mysql -p 9500:80 --network net-wp -v "C:\Users\saidl\Desktop\EPN\6 Semestre\Construcción y Evolución de Software\Práctica 3\ejercicio3\www\wordpress.env:/etc/mysql/conf.d/wordpress.env" -v mysql_data:/var/lib/mysql mysql:8
```
Nota: La ruta completa está  entre comillas para manejar los espacios y caracteres especiales.

3.3 

### ¿Qué observa en la carpeta db que se encontraba inicialmente vacía?
# COMPLETAR CON LA RESPUESTA A LA PREGUNTA

### Para que persista la información es necesario conocer en dónde wordpress almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/
En el esquema del ejercicio la carpeta del contenedor (b) es (COMPLETAR CON LA RUTA)

Ruta carpeta host: .../ejercicio3/www

### Crear un contenedor con la imagen wordpress en la red net-wp, configurar las variables de entorno WORDPRESS_DB_HOST, WORDPRESS_DB_USER, WORDPRESS_DB_PASSWORD y WORDPRESS_DB_NAME (los valores de estas variables corresponden a los del contenedor creado previamente)
# COMPLETAR CON EL COMANDO

### Personalizar la apariencia de wordpress y agregar una entrada

### Eliminar el contenedor y crearlo nuevamente, ¿qué ha sucedido?

# COMPLETAR CON LA RESPUESTA A LA PREGUNTA



