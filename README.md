##### Para saber los procesos ejecutados

`ps auxf`

##### Se puede ordenar con el 'sort' y pasarle la posicion con el flag -k (es la columna)

`ps auxf | sort -k 4`

##### En lista todo los paquetes instalados

`dpkg -l`

##### Crear un usuario

`sudo adduser <nombre usuario>`

##### Eliminar usuario

`sudo userdel <nombre usuario>`

##### Agregar usuario al grupo sudo

`sudo gpasswd -a <nombre usuario>`

##### Eliminar usuario de grupo sudo

`sudo gpasswd -d <nombre usuario> sudo`

##### Cambiar de usuario

`su - <nombre usuario>`

##### Muestra que grupo pertenece un usuario

`groups <nombre de usuario>`

##### Agrega un usuario a un grupo

`usermod -aG <grupo> <nombre usuario>`

##### Estatus de un servicio / sistema

`sudo systemctl status <nombre servicio>`

##### Listar servicios utilizados por SO

`sudo systemctl list-units -t service --all`

##### Logs de un servicios

`sudo journalctl -fu /var/log/<nombre servicio>`

#### Espacio en disco de archivos en uso

`sudo journalctl --disk-usage`

### Validar puertos que tienen un proceso activo usamos

`sudo netstat -tulpn` p = port n = numerica

### Repetir comando anterior con history

`history` - luego ejecutar el numero del comando anterior -> `!<numero del comando>`

### Buscar una palabra dentro de un archivo

`grep -i <palabra> <archivo>`

### Buscar dentro de un directorio puros archivos y con un nombre especifico en minuscula

`find <directory> -type f -name "*.png"`

### Buscar dentro de un directorio puros archivos y con un nombre especifico sin importar minuscula o mayuscula

`find <directory> -type f -iname "*.png"`

### Buscar archivos con cambios en los ultimos 10minutos

`find /etc/ -mtime 10`

### Buscar archivos con cambios en los ultimos 10minutos y con error

`find /etc/ -mtime 10 2` 2 significa archivos de error. 0 de entrada y 1 de salida.

### AWK patron para filtrar, reorganizar y darle formato a nuestros datos

{print $1} = imprime solo la primera columna
`awk '{print $1}' /var/log/nginx/access.log | sort | uniq -c | sort -nr`
