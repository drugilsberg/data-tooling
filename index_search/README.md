# Elasticsearch index search experiments

Early tests to build upon HuggingFace datasets to improving indexing/Search capabilities.

## Pre-requisites

Elasticsearch is launched in cluster through docker so go install Docker if not already done: https://docs.docker.com/get-docker/

The example is based on a forked version of dataset and some additional dependencies. Use `requirements.txt` to install all the necessary stuff. A conda en

## Run

* Go into the `index_search` folder and start Elasticsearch cluster

```
cd ./index_search
docker compose up
```

* Run the python script

```
python datasets_index_search.py
```

Note that it will start a ray instance which might require some ports to be open for local communication.

## TODO list

Improve datasets indexing capabilities
- [x] test switch to ngram indexing
- [x] add hash for each rows
- [x] parallel processing using ray and dataset shards
    - [x] enable re-connection to existing index in ES
    - [x] enable continuing indexing process
    - [x] ensure no duplicate
- [ ] allow export of search results in arrow for datasets or jsonl for export => specialized filter operation?
- [ ] instantiate datasets from elasticsearch query
- [ ] secure elasticsearch cluster: free read, protected write
- [ ] allow update on the dataset to be reflected with index update