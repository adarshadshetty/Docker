docker pull mongo-express


docker run --network some-network -e ME_CONFIG_MONGODB_SERVER=some-mongo -p 8081:8081 mongo-express




Then you can hit http://localhost:8081 or http://host-ip:8081 in your browser


mongo express -->

docker run -p 27071:27017 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=password --name mongodb --net mongo-network -d mongo

[mongodb] --> This is running on mongodb network 


docker run -d \
-p 8081:8081\
-e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
-e ME_CONFIG_MONGODB_ADMINPASSWORD=password \
-e ME_CONFIG_MONGODB_SERVER=mongodb \
--net mongo-network \
--name mongo-express \
mongo-express





 docker run -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password --name mongodb --net mongo-network -d mongo





-----------------------------------------------------------------------------------------------

Python Flask Project 




-------------------------------------------------------------------------------------------------
Docker Nodejs Project 

npm init -y --> and next configure the file 


To Build Image 

docker build -t shettyadarsha/hey-nodejs:0.0.1.RELEASE

docker container ls

To run this image 

docker container run -d -p 3000:3000 shettyadarsha/hey-nodejs:0.0.1.RELEASE

to stop container 

docker container 'containerId or Container Name'
