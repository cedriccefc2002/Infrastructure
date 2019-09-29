# MongoDB

[官方網址](https://www.mongodb.com/)

## 安裝

資料目錄：/home/cefc/Data/Docker/mongo/db/

```bash
datapath="/home/cefc/Data/Docker/mongo/db/"
mkdir -p ${datapath}
sudo docker run \
    -d \
    -p 27017:27017 \
    -v ${datapath}:/data/db \
    --restart always \
    --name mongo \
    mongo:latest \
    --wiredTigerCacheSizeGB 1
```
