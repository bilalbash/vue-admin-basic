# vue-admin

### Project setup
Go to the root Directory of this project and than install it via the following command:
```
yarn install
```
Once the setup is finished you need to [install and setup the docker](https://github.com/bilalbash/vue-admin-basic#setting-up-docker)  as well. Once completing the docker setup  [run the project](https://github.com/bilalbash/vue-admin-basic#running-the-project). 

### Setting Up Docker 
After setting up local project also load api from the following docker command:
###### Step # 1
1. Download and install docker via [this link](https://www.docker.com/products/docker-desktop) so that the icon of docker will start appearing on the top right corner of your screen indicating that docker is successfully installed and running in the background.
2. make sure you already have the file named: `docker-compose.yaml` in the root directory of your project.
3. now goto the terminal and move to the root directory of vue-admin project
4. type the following command:
```
docker-compose up
```
###### Step # 2
when this process is finished and you will know when nothing seems to be processing and the screen will be stop with `code 1` .
now press `ctrl + c` and than you need to run this command again:
```
docker-compose up
```
once finished you will be able to see the following message at the end:
```
db_1       | Version: '5.7.22'  socket: '/var/run/mysqld/mysqld.sock'  port: 3306  MySQL Community Server (GPL)
```
###### Step # 3
than open another tab and type in the following command:
```
docker-compose exec backend sh
```
###### Step # 4
this command will take you inside docker container. inside it run the following command:
```
./start.sh
```
The process will be completed with the following message:
```
Database seeding completed successfully. 
```
###### Step # 5
Meanwhile you will still be inside docker container for another command and you can also consume and see api details by using the following link:
```
http://localhost:8000/api/documentation
```

### Running the Project
#### Run for development (local setup)

###### Step # 1 : start docker
Assuming you already completed the setup of this project now just start the Docker by following steps 2 to 5 of [Setting Up Docker](https://github.com/bilalbash/vue-admin-basic#setting-up-docker)
###### Step # 2 : Start the Dev server
Open another tab and than Run the development server with the following command:
```
yarn serve
```
#### Run for production
...

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
