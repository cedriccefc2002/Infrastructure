# Logstash

## 安裝

[說明](https://www.elastic.co/guide/en/logstash/current/docker-config.html)

- 設定目錄：/home/cefc/Data/Docker/Logstash/pipeline/
- Elasticsearch 網路：elk-network name=elasticsearch

/home/cefc/Data/Docker/Logstash/pipeline/default.conf

```conf
input {
  beats {
    port => 5044
  }
}

output {
  elasticsearch {
    hosts => "elasticsearch:9200"
    manage_template => false
    index => "%{[@metadata][beat]}-%{[@metadata][version]}-%{+YYYY.MM.dd}" 
    document_type => "%{[@metadata][type]}" 
  }
}
```

```sh
pipelinepath="/home/cefc/Data/Docker/Logstash/pipeline/"
mkdir -p ${pipelinepath}
sudo docker run \
-d \
--restart always \
--name logstash \
--net elk-network \
-p 5044:5044 \
-v ${pipelinepath}:/usr/share/logstash/pipeline/ \
docker.elastic.co/logstash/logstash:7.4.0
```
