# docker-nextcloud

Nextcloud 容器化部署

## 使用说明

```sh
git clone https://github.com/wojiushixiaobai/docker-nextcloud --depth 1
cd docker-nextcloud
```

```sh
cp env.example .env
```

```sh
vim .env
```

```vim
# Description: Environment variables for Nextcloud
COMPOSE_PROJECT_NAME=nd

# 数据库配置，POSTGRES_PASSWORD 需要填一下
POSTGRES_USER=nextcloud
POSTGRES_PASSWORD=************
POSTGRES_DB=nextcloud

# Nextcloud 管理员账号密码，密码自己填，首次登录完成后自己在后台改。
NEXTCLOUD_ADMIN_USER=admin
NEXTCLOUD_ADMIN_PASSWORD=********

# Nextcloud 信任域配置，你访问的 URL 地址是什么就填什么，多个用空格隔开，填错页面会看到对应的提示。
# 比如你访问的是 http://192.168.1.100:8080 那么就填 NEXTCLOUD_TRUSTED_DOMAINS="192.168.1.100:8080"
NEXTCLOUD_TRUSTED_DOMAINS=""

# Web 访问端口
HTTP_PORT=8080
```

```sh
docker compose up -d
```