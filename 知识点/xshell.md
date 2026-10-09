ec：docker compose -f /home/export-center/docker-compose-ecv3.yml logs --tail=2000 -f

das：docker compose -f /home/data_analysis_service/docker-compose-dasv3.yml logs --tail=2000 -f

查找某个关键词 -- 少了-f -f是持续跟踪日志

docker compose -f /home/data_analysis_service/docker-compose-dasv3.yml logs --tail=2000 | grep "emptyFieldTypeList"

看docker docker ps