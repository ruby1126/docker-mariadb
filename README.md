# docker-mysql
mysql in docker

### 建立容器
<p>下載所有檔案，打開powershell，執行</p>
<pre><code>docekr-compose up -d</code></pre>

### 使用adminer對mysql進行圖形化操作
<p>打開docker-compose.yml 加入</p>
<pre><code>version: '3.7'
services:
  mysql:
    image: mariadb
    environment:
      MYSQL_ROOT_PASSWORD: password
    volumes:
      - mysqlvolume:/var/lib/mysql
    ports:
      - 3316:3306
  adminer:
    image: adminer
    restart: always
    ports:
      - 8080:8080
volumes:
  mysqlvolume:
</code></pre>
