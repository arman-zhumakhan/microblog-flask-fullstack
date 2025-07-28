# Welcome to Microblog!

This is the Microblog project with Flask backend. Frontend is in Bootstrap, HTML.


## Installation
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
