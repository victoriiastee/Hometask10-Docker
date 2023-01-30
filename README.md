# Hometask10-Docker
Prerequisites: 
[Docker](https://docs.docker.com/engine/install/ubuntu/)
or 
[Docker Desktop](https://docs.docker.com/desktop/install/windows-install/); 

I have already installed Docker Desktop on my Windows and Docker plugin on my VScode.
## Task 1 
To complete this task I: 
* Created [Dockerfile](https://github.com/victoriiastee/Hometask10-Docker/blob/main/Task-1/Dockerfile);
* Created Docker Image for Apache 2.4 based on Dockerfile;
* Run container based on this Image. 
 
 To run it You need to clone this [directory](https://github.com/victoriiastee/Hometask10-Docker/tree/main/Task-1) and execute following comands: 
 ```
 docker build -t slimak:new .
 ```
 ```
 docker run -d -p 8080:80 slimak:new
 ```
 So, You Will see this on Your localhost on port 8080:
 ![](https://user-images.githubusercontent.com/102364456/215574820-f4abfbef-80d1-4030-8ff3-e3f1f2de40e4.jpg)
 
 ## Task 2
 
 To complete this task I: 
* Prepared private and public network;
```
docker network create private --internal
docker network create public
```
* Created [Dockerfile](https://github.com/victoriiastee/Hometask10-Docker/blob/main/Task-2/Dockerfile) based on ubuntu with the ping command;
* I built an image based on Dockerfile;
```
docker build -t myping .   
```
* Ran containers;
```
docker run --name my-public -d --network public myping  
docker run --name my-private -d --network private myping
```
![](https://user-images.githubusercontent.com/102364456/215574903-4377df46-2694-498f-8a7e-d9a2ebeaf30d.jpg)
* Connect private to public container;
```
docker network connect private my-public
```
* Inspected access to public IP addresses:
```
docker network inspect public
```
![](https://user-images.githubusercontent.com/102364456/215575144-ddc7629a-a044-4438-aa28-6536998381cc.jpg)

* Inspected access to private;
```
docker network inspect private
```
![](https://user-images.githubusercontent.com/102364456/215575029-58f53210-328f-4a35-bbf4-79135a7ad8dc.jpg)
*Ping results:
```
docker exec -it my-private /bin/bash
docker exec -it my-public
```

![](https://user-images.githubusercontent.com/102364456/215575415-1848dc85-3ad9-441f-9723-3ed747154653.jpg) 

![](https://user-images.githubusercontent.com/102364456/215575339-193258c2-2f49-46da-b7c7-5ef939b69adb.jpg)

![](https://user-images.githubusercontent.com/102364456/215575242-3db037c3-dc93-4798-9d26-99b24dbef56c.jpg) 
### Thank You!
