# docker-postgres-cn
docker postgres with zh-cn.UTF-8 locale

docker-compose sample

```
services:
  postgres:
    image: postgres
    container_name: postgres
    restart: always
    ports:
      - '5432:5432'
    volumes:
      - ./db_data:/var/lib/postgresql/data
      # postgres version >= 18时
      # ./db_data:/var/lib/postgresql
    environment:
      TZ: Asia/Shanghai
      POSTGRES_INITDB_ARGS: "--encoding=UTF8 --locale=zh_CN.UTF8 --lc-messages=en_US.UTF8"
      # POSTGRES_INITDB_ARGS: "--encoding=UTF8 --locale=zh_CN.UTF8"
      POSTGRES_DB: test
      POSTGRES_USER : user
      POSTGRES_PASSWORD: pass
```
