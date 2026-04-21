Инициализируй кластер (если еще не сделал):

Bash
docker swarm init
Создай секрет (тот самый, который не идет в Git):

Bash
echo "supersecretpassword" | docker secret create db_password -
Пометь ноду для базы данных:

Bash
docker node update --label-add storage=true $(docker node ls -q)
Запускай стек:

Bash
docker stack deploy -c docker-stack.yml myapp
