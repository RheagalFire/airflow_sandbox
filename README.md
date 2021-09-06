## Airflow Sandbox
Airflow is an automating tool for automaring Data Pipelnes.

## Setup Airflow Locally 
- Install and Start Docker.
- Run below command in cmd.
```
docker pull puckel/docker-airflow
```
- List Images 
```
docker images
```
Jump into containers cmdline either by using dockerdesktop or by 
```
docker exec -ti <container name> bash
```
Container Name can be checked using `docker ps`

## Running A DAG 
- make a DAG directory in your local machine. 
- Mount a volume to ypur container that maps your DAG dir to container DAG directory. 

```
docker run -d -p 8080:8080 -v /path/to/dags/on/your/local/machine/:/usr/local/airflow/dags  puckel/docker-airflow webserver
```
- This will start a webserver in localhost:8080
## Get Started with a Simple DAG
- cp the given example.py and paste it inside the DAG directory of your local machine. 
- check your webserver(localhost)(might take some time to update)
- `airflow list_dags`(in container's cmdline) to see all the DAGS. 
- Explore the UI or run a task using 
`airflow test Helloworld task_1 1`
