# Simple Java Maven Dockerized Application #

Build the image using the following command
To install maven(in order to package the code as a war file),

```bash
$ sudo apt install maven -y
```
Clone the repo;

```bash
$ git clone https://github.com/astiksubudhi/Docker-Simple-Java-Project.git
```
Switch to the directory;
```bash
$ cd <DirectoryName>
```

To verify the files;
```bash
$ ls -l
```

Package the application code using maven goals(it'll delete the existing "target" folder and create new "target" folder, inside which application .war file will be available);

```bash
$ mvn clean package
```
To build the docker image;
```bash
$ docker build -t javamavenfirst:v1 
```
To check the created image;
```bash
$ docker images
```

Run the Docker container using the command shown below.
(Here the docker engine will run the container from image javamavenfirst:v1 in detached mode and with port mapping 8080:8080 )

```bash
$  docker run -d -p 8080:8080 --name javamavenapp javamavenfirst:v1
```

The application will be accessible at (http:PublicIPofVM:8080/WarFileName/)

In my machine I am using a self hosted Ubuntu VM(Inside Proxmox VE) in which the docker is running so I am able to access the application using VM's IP (http://192.168.1.190:8080/WarFileName/)

