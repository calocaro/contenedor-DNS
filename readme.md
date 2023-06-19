# Practica DNS
Aquí tienes un ejemplo de cómo podría ser el archivo `README.md` para describir las opciones del `docker-compose.yml` utilizado en el escenario de configuración del contenedor BIND9:

# Configuración del Contenedor DNS con BIND9

Este repositorio contiene un archivo `docker-compose.yml` que se utiliza para configurar un contenedor DNS utilizando la imagen oficial de BIND9. A continuación, se describe cada una de las opciones presentes en el archivo `docker-compose.yml`:

## Opciones del archivo docker-compose.yml

### Versión

```yaml
version: '3'
```

La versión de la sintaxis del archivo `docker-compose.yml`. En este caso, se utiliza la versión 3.

### Servicios

```yaml
services:
  bind9:
    ...
```

La sección `services` define los servicios que se crearán utilizando Docker Compose. En este caso, se define un servicio llamado `bind9` para el contenedor BIND9.

### Imagen

```yaml
image: bind
```

La imagen a utilizar para el servicio `bind9`. En este caso, se utiliza la imagen oficial de BIND9 llamada `bind`.

### Volumenes

```yaml
volumes:
  - ./data:/etc/bind
  - ./logs:/var/log/bind
```

Los volúmenes especificados para el servicio `bind9`. En este caso, se mapean los directorios locales `./data` y `./logs` a los directorios dentro del contenedor `/etc/bind` y `/var/log/bind`, respectivamente. Esto permite persistir la configuración y los registros de BIND incluso después de reiniciar el contenedor.

### Puertos

```yaml
ports:
  - "53:53/tcp"
  - "53:53/udp"
```

Los puertos que se exponen en el contenedor. En este caso, se exponen los puertos `53` tanto en TCP como en UDP para permitir el tráfico DNS.

### Reinicio automático

```yaml
restart: always
```

La opción `restart` configura el comportamiento de reinicio del contenedor. En este caso, se utiliza `always`, lo que significa que el contenedor se reiniciará automáticamente si se detiene o se reinicia el sistema.

---

Este archivo `README.md` proporciona una descripción de las opciones utilizadas en el archivo `docker-compose.yml` para configurar el contenedor BIND9. Puedes utilizar esta información como referencia al trabajar con el contenedor DNS y modificar la configuración según tus necesidades.

Si tienes alguna pregunta adicional o necesitas más ayuda, ¡no dudes en preguntar!
