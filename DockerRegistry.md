# Docker Registry

[官方網址](https://hub.docker.com/_/registry)

## 安裝

資料目錄：/home/cefc/Data/Docker/DockerRegistry/Data

```bash
datapath="/home/cefc/Data/Docker/DockerRegistry/Data"
mkdir -p ${datapath}
sudo docker run \
    -d \
    -p 5000:5000 \
    -v ${datapath}:/var/lib/registry \
    --restart always \
    --name registry \
    registry:latest
```

## pull Image

```bash
sudo docker pull nginx:latest
sudo docker tag nginx localhost:5000/nginx:demo
sudo docker push localhost:5000/nginx:demo
```

## 問題排除

- Insecure Registry
    1. 修改設定 `/etc/docker/daemon.json`

        ```json
        {
        "insecure-registries" : ["myregistrydomain.com:5000"]
        }
        ```

    1. [官方說明](https://docs.docker.com/registry/insecure/)

## 參考資料

- [docker-registry](https://junior78469.blogspot.com/2018/07/docker-registry.html)
