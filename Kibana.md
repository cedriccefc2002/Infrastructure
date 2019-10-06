# Kibana

## 安裝

[Url](https://hub.docker.com/_/kibana)
[說明](https://www.elastic.co/guide/cn/kibana/current/docker.html)

[設定環境變數](https://www.elastic.co/guide/cn/kibana/current/docker.html#docker-env-config)
SERVER_HOST=0.0.0.0 讓外部可以瀏覽

Elasticsearch 網路：elk-network name=elasticsearch

```sh
sudo docker run \
-d \
--restart always \
--name kibana \
--net elk-network \
-p 5601:5601 \
-e "SERVER_HOST=0.0.0.0" \
docker.elastic.co/kibana/kibana:7.4.0
```

[UI](http://127.0.0.1/5601)
