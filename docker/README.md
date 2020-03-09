# docker

## 環境

* ubuntu 18.04


## 安裝

https://docs.docker.com/install/linux/docker-ce/ubuntu/

```
sudo apt-get update
```

```
 sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

```
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

```
sudo apt-get update
```

```
sudo apt-get install -y docker-ce docker-ce-cli containerd.io
```

### user

```
sudo usermod -aG docker your-user
```

## 使用

### docker pull

```
docker pull nginx
```

### docker run

```
docker run -p 8080:80 -d nginx
```

### docker ps

```
docker ps -a
```

### docker rm

```
docker rm -f 143c0792e94f
```

#### volume

```
docker run -p 8080:80 -v $(pwd)/web:/usr/share/nginx/html -d nginx
```


### docker build


Dockerfile

```
FROM nginx

COPY web /usr/share/nginx/www
COPY nginx.conf /etc/nginx/conf.d/default.conf
```


```
docker build -t web:0.0.1 .
```


### docker images

```
docker images
```

### docker rmi

```
docker rmi web
```
