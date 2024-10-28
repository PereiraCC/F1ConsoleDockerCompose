# F1 Console Docker compose

## Pasos para ejecutar el app

1. Instalar docker [Docker Desktop](https://docs.docker.com/desktop/)
2. Clonar este repositorio localmente.
3. Navegar a la carpeta local de este proyecto en la terminal
4. Crear el archivo **.env** con base al archivo **.env.template**. 
    - Nota: Solamente indicar el valor del Password.
5. Ejecutar el comando ```docker compose up -d```
6. Connectarse a la BD mediante un gestor con las siguientes credenciales
    - SERVER => localhost | El container levanta en puerto 1433
    - USERBD => sa
    - PASSWORD => yourPassword
    - Algunos Gestores que se pueden usar
        - [TablePlus](https://tableplus.com/)
        - [Azure Data Studio](https://azure.microsoft.com/en-us/products/data-studio)
        - [SSMS](https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16)
7. Ejecutar el script de Data inicial archivo **initData.sql**
8. Ejecutar el comando ```docker exec -it f1-app /bin/bash``` esto permite entrar a la consola del container.
9. Dentro de la consola ejecutar el comando ```dotnet F1Console.dll``` y lograr ejecutar la app de F1 Console.

### Notas

1. Para salir de la terminar del container usar el comando ```exit```
2. Para limpiar los container, volume y network ejecutar el comando ```docker compose down --volumes```
3. Para eliminar las imagenes ejecutar los comando
    - ```docker image rm -f IDImages```

### Imagen de docker
[F1 Console Image](https://hub.docker.com/repository/docker/pereira00/f1console/general)

### Codigo fuente
[F1 Console source](https://github.com/PereiraCC/F1Console)

##### Carlos Pereira, 2024