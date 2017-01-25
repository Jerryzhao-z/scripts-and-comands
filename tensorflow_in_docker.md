# install tensorflow jupyter in docker under Win10

## 1. install docker
the most easy way to install Docker in Windows is by [**Docker Toolbox**](https://www.docker.com/products/docker-toolbox)
## 2. create a new VM with docker
After the installation, You would find a new terminal called **Docker Quickstart Terminal**
tape in this terminal, create a docker machine named **vd** in virtualbox
```bash
docker-machine create vd -d virtualbox
```
![virtualbox](http://upload-images.jianshu.io/upload_images/2839127-4b90e33c8fba3425.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
## 3. Get tensorflow image or start tensorflow image
in CMD
```bash
FOR /f "tokens=*" %i IN ('docker-machine env --shell cmd vd') DO %i

docker run -it -p 8888:8888 -e PASSWORD=password tensorflow/tensorflow
```
More details, consult [Docker Hub](https://hub.docker.com/r/tensorflow/tensorflow/)
The first command configure some environment variables

And the second run a docker image of tensorflow in port 8888 

The password here is used to login the Jupyter.
## 4. Get URL of Jupyter
in Docker QuickStart Terminal
```bash
docker-machine ls
```
get all the docker machine URL

![docker machine](http://upload-images.jianshu.io/upload_images/2839127-d684b0ecf3f5357d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Use Jupyter in **http://192.168.99.102:8888** and login with the password

![jupyter](http://upload-images.jianshu.io/upload_images/2839127-29cc4bb8a9a839a5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
## 5. Stop the docker
get the id of the docker and stop it
```bash
docker ps -a

docker stop _docker_id_
```


reference: [在Windows使用TensorFlow](http://www.jianshu.com/p/fbb16a40fac9)