version: "3.1"
services:
mysql:
image: mysql/mysql-server:latest
container_name: mysql
environment:
MYSQL_ROOT_PASSWORD: /run/secrets/my_secret
secrets:
- my_secret

secrets:
my_secret:
file: ./my_secret.txt
 external:
    name: mydata

//

Docker mounts a file under /run/secrets/<secret_name> in the services. These files are never persisted in disk, but are managed in memory.

Each service uses environment variables to specify where the service should look for that secret data.

The decrypted secret is mounted into the container in an in-memory filesystem. The location of the mount point within the container defaults to /run/secrets/<secret_name>  
