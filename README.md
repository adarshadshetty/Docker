# Docker
Docker Project And Resources

Implementing Docker File for different Application.

### Docker push steps
1. docker images
##### hello-world  = image name

2. docker tag hello-world shettyadarsha/hello-worldapp:v1.0

3. docker images
  ###### shettyadarsha/hello-worldapp   v1.0        d2c94e258dcb   12 months ago   13.3kB


5. docker push shettyadarsha/hello-worldapp:v1.0



## download docker compose
$ sudo curl -L "https://github.com/docker/compose/releases/download/1.24.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

## Give permission
$ sudo chmod +x /usr/local/bin/docker-compose
	
## How to check docker compose is installed or not
$ docker-compose --version

