
Initialize the swarm node with swarm init



Create a docker secret for mysql password

echo "MyRootPass123" | docker secret create myPass - 

echo "myuser" | docker secret create pass -

printf "hehe" | docker secret create my_secret -

Create secret from stdin values


Create secret from file contents

echo "MyPass" >> secretFile
docker secret create my_data ./secretFile
 
docker secret create [OPTIONS] SECRET [file|-]
Creates a secret using standard input or from a file for the secret content.

The docker secrets stored in /run/secrets/<secret_name> files of the container
. For example:
docker run --name app-mysql -e MYSQL_ROOT_PASSWORD=myPass -d mysql:5.6

docker secret ls

docker secret ls -q

docker inspect jjwmza01wguy61cetxqezwr80

To remove secret
docker secret rm mysecr

Derlete all secrets

docker secret rm $(docker secrets ls -q)



