- 把目录下的sh.example拷贝到mongodump容器映射的data目录, 目的是能够在具有mongodump命令的容器里能够执行批处理
- 安装cron计划任务  apt-get install cron
- 安装rsyslog  apt-get install rsyslog, 这样/var/log下才有cron.log
- crontab -e 去编辑, 25 8    * * *  /data/mongodb_bak/mongodb_bak.sh  (每天8：25执行)
- */120 *    * * *  /data/mongodb_bak/mongodb_bak.sh (每隔120分钟执行)