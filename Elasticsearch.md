# Elasticsearch

- [官網](https://www.elastic.co/cn/)
- [原始碼庫](https://github.com/elastic/elasticsearch)

## 安裝

- [官網說明](https://www.elastic.co/guide/en/elasticsearch/reference/6.4/docker.html)

- 資料目錄：/home/cefc/Data/Docker/Elasticsearch/db/
- 網路：elk-network

```sh
datapath="/home/cefc/Data/Docker/Elasticsearch/db/"
mkdir -p ${datapath}
sudo docker network create elk-network
sudo docker run \
-d \
--net elk-network \
--restart always \
--name elasticsearch \
-p 9200:9200 \
-p 9300:9300 \
-e "discovery.type=single-node" \
-v ${datapath}:/usr/share/elasticsearch/data \
docker.elastic.co/elasticsearch/elasticsearch:7.4.0
```

Test

```sh
curl http://127.0.0.1:9200/_cat/health
```
