# Research
For my research work on mini-demand-side-platforms, I utilized JupyterLab as my primary tool for conducting analyses. All research tasks and analyses were carried out within this environment.

Also, this repository has a simple example of how to use the [mini-demand-side-platform/feature-store](mini-demand-side-platform/feature-store) during training and inference.

## Requirements
- poetry
- docker
- docker-compose 
- make

## Setup
#### 1. active databases 
```
git clone git@github.com:mini-demand-side-platform/databases.git
cd databases 
make run-all-with-example-data
```
#### 2. active feature store
```
docker run -it --rm --network databases_default -p 8000:8000 \
	-e olap_host='postgresql' \
	-e cache_host='redis' \
	raywu60kg/feature-store:0.1.0
```

#### 3. install python packages
```
poetry install
```

#### 4. activate jupyterlab
```
poetry run jupyter lab
```

