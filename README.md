# Welcome to Microblog!

This is the Microblog project with Flask backend. Frontend is in Bootstrap, HTML.


## Installation
### Docker
```
docker build -t microblog:latest .
docker run --name microblog -d -p 8000:5000 --rm microblog:latest
```

### Manually run locally
1. Create a virtual env and install dependencies
```
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

2. Create a .env file and write env variables
```
cp .env.example .env
vim .env
```

3. Run
```
flask run
```

## ElasticSearch for searching a post

1. Run Elasticsearch with local Docker
```
docker run --name elasticsearch -d --rm -p 9200:9200 \
    --memory="2GB" \
    -e discovery.type=single-node -e xpack.security.enabled=false \
    -t docker.elastic.co/elasticsearch/elasticsearch:9.0.3
```
2. Add its URL to .env

## Redis server for a task queue
1. Install a Redis server

MacOS
```
brew install redis
```

Ubuntu Linux
```
sudo apt-get install redis-server
```

2. Create a supervisor confuguration
```
rq worker microblog-tasks
```

## Testing
Start a Python interpreter in the context of the app
```
flask shell
```
