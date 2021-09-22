# vue-admin

## Project setup
```
yarn install
```
Once the setup is finished than run the [the development server](https://github.com/bilalbash/vue-admin-basic#running-the-dev-server).

### Setting Up Docker 
After setting up local project also load api from the following docker command:
1. install docker so that the icon of docker will start appearing on the top right corner of your screen indicating that docker is successfully installed and running in the background.
2. make sure you already have the file named: `docker-compose.yaml` in the root directory of your project.
3. now goto the terminal and move to the root directory of vue-admin project
4. type the following command:
```
docker-compose up
```
when this process is finished and you will know when nothing seems to be processing and the screen will be stop with `code 1` .
now press `ctrl + c` and than you need to run this command again:
```
docker-compose up
```
once finished you will be able to see the following message at the end:
```
db_1       | Version: '5.7.22'  socket: '/var/run/mysqld/mysqld.sock'  port: 3306  MySQL Community Server (GPL)
```
than open another tab and type in the following command:
```
docker-compose exec backend sh
```
this command will take you inside docker container. inside it run the following command:
```
./start.sh
```
The process will be completed with the following message:
```
Database seeding completed successfully. 
```
Meanwhile you will still be inside docker container for another command and you can also consume and see api details by using the following link:
```
http://localhost:8000/api/documentation
```

### Running the Dev server
Open another tab and than Run the development server with the following command:
```
yarn serve
```

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
