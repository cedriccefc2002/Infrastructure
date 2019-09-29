# RabbitMQ

[消息代理](https://zh.wikipedia.org/wiki/%E6%B6%88%E6%81%AF%E4%BB%A3%E7%90%86) 軟體

## 安裝

資料目錄：/home/cefc/Data/Docker/RabbitMQ/db/

```bash
datapath="/home/cefc/Data/Docker/RabbitMQ/db/"
mkdir -p ${datapath}
sudo docker run \
    -d \
    -p 5672:5672 \
    -p 15672:15672 \
    -v ${datapath}:/var/lib/rabbitmq \
    --memory 1024m \
    --memory-swap 1024m \
    --restart always \
    --hostname rabbitmq \
    --name rabbitmq \
    rabbitmq:management
```

default username and password of guest / guest
