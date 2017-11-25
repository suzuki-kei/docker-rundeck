# docker-rundeck

## initial setup

    ssh-keygen -t rsa -b 4096 -N '' -C 'rundeck' -f ./volumes/rundeck/var/lib/rundeck/.ssh/id_rsa

## run

    docker-compose up -d

