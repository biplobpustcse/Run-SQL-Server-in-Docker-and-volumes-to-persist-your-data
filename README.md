# Run SQL Server in Docker and volumes to persist your data

##### Learn how to run an instance of SQL Server in a Docker Container.
##### This is a great way to run and test applications against a local database. Try out all your changes locally before going to dev, test or production!

#### Add volumes to persist your data, even if you delete the docker container!

#### SQL Server Docker Hub page:
https://hub.docker.com/_/microsoft-mssql-server

#### Documentation for volumes and persisting data:
https://learn.microsoft.com/en-us/sql/linux/sql-server-linux-docker-container-configure?view=sql-server-ver16&pivots=cs1-bash#persist

## Let's start

#### Step #01: 
###### Download Docker Image.
###### command
```
docker pull mcr.microsoft.com/mssql/server:2019-latest
```
#### Step #02-a: 
###### How to use this Image or create container (not persist your data)
###### command
```
docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=yourStrong(!)Password" -e "MSSQL_PID=Evaluation" -p 1433:1433  --name sqlpreview --hostname sqlpreview -d mcr.microsoft.com/mssql/server:2019-preview-ubuntu-22.04
```

#### Step #02-b: 
###### How to use this Image or create container with volumes (persist your data)
###### command
```
docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=dat55a!21122019" -p 1433:1433 --name sql2019 -v F:/DockerDatabase/DockerDataVolume/sql2019/SqlData/data:/var/opt/mssql/data -v F:/DockerDatabase/DockerDataVolume/sql2019/SqlData/log:/var/opt/mssql/log -v F:/DockerDatabase/DockerDataVolume/sql2019/SqlData/secrets:/var/opt/mssql/secrets -d mcr.microsoft.com/mssql/server:2019-latest
```
![image](https://github.com/biplobpustcse/Run-SQL-Server-in-Docker-and-volumes-to-persist-your-data/assets/59637279/8940028c-05aa-4957-bb8c-fc9d03461001)

![image](https://github.com/biplobpustcse/Run-SQL-Server-in-Docker-and-volumes-to-persist-your-data/assets/59637279/b416b75d-bfed-4a56-856a-95b80598e874)

![image](https://github.com/biplobpustcse/Run-SQL-Server-in-Docker-and-volumes-to-persist-your-data/assets/59637279/826ce3c0-499d-4541-8807-809521d9e3d4)
