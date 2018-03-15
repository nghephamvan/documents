Setup enviroment and data

=================================================================
#### For MAC
Link: 
[Download Docker for MAC](https://docs.docker.com/docker-for-mac/install/#download-docker-for-mac)

1. Install and run Docker.
If Mounts denied on Mac, you can configure shared paths from Docker -> Preferences... -> File Sharing.

=================================================================

#### For Windows 10 (Administrator)
Link:
[Download Docker for Windows 10](https://download.docker.com/win/stable/Docker%20for%20Windows%20Installer.exe)

1. Install Docker.
1.1 Vitualization is Enabled 
1.2 Hyper V Manager is ennabled (OR VitualBox)
- Check existed LinuxVM in Hyper V. Setting DockerNAt is internal in  Virtual Switch Manager (Hyper V)

References: https://docs.docker.com/docker-for-windows/troubleshoot/#virtualization

Note: Run Windows PowerShell for command line

=================================================================

#### For Windows 7 (Administrator)
##### Updating...

=================================================================

2. Change file config.json in server folder 
For development

```bash
"username": "qwertup",
"password": "buffered07",
"database": "node_api_dev",
"host": "pg",
```

3. Run command for build and migrate data (Read more docker-compose.yml)
// Build container 
`docker-compose build`

// start container
`docker-compose up -d`

//show container is running
`docker ps`

// access Node
`docker exec -it <container name> sh`

// Migrate DB table
`sequelize db:migrate`

// Migrate database seeder
`sequelize db:seed`

// or (files in seeders folder)
`sequelize db:seed --seed <seed file name>`

// access postgres
`docker exec -it <container name> bash`

// check database migrate
`psql -d node_api_dev -U qwertup`
`select * from "Sports";`

// check page running
Access link: http://localhost/

Other command line:
// Stop container
`docker-compose stop`

// show all container
`docker ps -a`

Note: If you want shutdown all container and re-create
`docker-compose down`
