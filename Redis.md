# Redis

快取資料庫

## 安裝

資料目錄：/home/cefc/Data/Docker/Redis/db/

```bash
datapath="/home/cefc/Data/Docker/Redis/db/"
mkdir -p ${datapath}
sudo docker run \
    -d \
    -p 6379:6379 \
    -v ${datapath}:/data \
    --restart always \
    --name redis \
    redis:latest \
    redis-server --appendonly yes
```
