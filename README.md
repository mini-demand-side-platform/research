# Research
For my research work on mini-demand-side-platforms, I utilized JupyterLab as my primary tool for conducting analyses. All research tasks and analyses were carried out within this environment.

## Requirements
- poetry
- docker-compose 

## Setup
#### 1. active databases 
```
git clone git@github.com:mini-demand-side-platform/databases.git
cd databases 
docker compose up
```
#### 2. active feature store
```
docker run -it --rm --network databases_default -p 8000:8000 \
	-e olap_host='postgresql' \
	-e cache_host='redis' \
	raywu60kg/feature-store:0.1.0rc0
```

#### 3. install python packages
```
poetry install
poetry 
```

#### 4. activate jupyterlab
```
poetry run jupyter lab
```

