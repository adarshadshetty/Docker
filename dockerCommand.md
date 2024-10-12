```
docker run imagesName:latest
```

```
docker pull images
```

```
docker run imageName ls
```

```
PS C:\Users\HP> docker run busybox ls
bin
dev
etc
home
lib
lib64
proc
root
sys
tmp
usr
var
PS C:\Users\HP>
```


```
docker run busybox ls ./bin
```

#### postgres docker image setup
```
docker pull postgres:11.5
```

```
 docker run --name postgres -e POSTGRES_PASSWORD=pass123 -d postgres:11.5
```

```
PS C:\Users\HP> docker ps
CONTAINER ID   IMAGE           COMMAND                  CREATED          STATUS          PORTS      NAMES
4f8aadb7c184   postgres:11.5   "docker-entrypoint.s…"   12 minutes ago   Up 12 minutes   5432/tcp   postgres
PS C:\Users\HP>
```  

- Docker container running on port 5432 
- Stop the container and open the port

```
docker stop containerID
```

```
PS C:\Users\HP> docker rm $(docker ps -a -q)
4f8aadb7c184
d7ebe4dd4e2a
b32b59bec0ad
be1e09f35c05
40371357888d
9836f3243d34
PS C:\Users\HP>
```

- Removes all the container (docker ps -a -q: Lists the container IDs of all containers (both running and stopped).)
```
docker rm $(docker ps -a -q)
```

```
PS C:\Users\HP> docker run --name postgres -e POSTGRES_PASSWORD=pass123 -p 8000:5432 -d postgres:11.5
68c7a1f72e1fb4a932b7f74296dce87dc07955c3c6f137e39a85c17e24387c49
PS C:\Users\HP> docker ps
CONTAINER ID   IMAGE           COMMAND                  CREATED         STATUS         PORTS                    NAMES
68c7a1f72e1f   postgres:11.5   "docker-entrypoint.s…"   7 seconds ago   Up 5 seconds   0.0.0.0:8000->5432/tcp   postgres
PS C:\Users\HP>

```

- Port Binding
```
docker run --name postgres -e POSTGRES_PASSWORD=pass123 -p 8000:5432 -d postgres:11.5
```

```
sudo apt install postgresql-client-common
```

```
sudo apt install postgresql-client
```


```
psql -h localhost -p 8000 -U postgres
```

```
\l
```
# Image

```
\q
```

```
docker stop postgress
```

```
docker rm containerID
```

### Let's Dockerize the RealWorld Application (Jira Application)
#### -----------------------------------------------------------
