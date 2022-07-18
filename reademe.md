ESAME ITS - PRIMA PROVA

    Parte 1 - Docker

        creo il docker file --> C:\Users\user\Desktop\Prima prova DEVO\Prima prova DEVO\backend\Dockerfile

        creo il .dockerignore --> C:\Users\user\Desktop\Prima prova DEVO\Prima prova DEVO\backend\.dockerignore

        creo il docker-compose --> C:\Users\user\Desktop\Prima prova DEVO\Prima prova DEVO\docker-compose.yml
            - inserite le variabili env tramite env_file
            - inseriti i volumi per i servizi di db e pgadmin

        nell'oggetto pool ho cambiato la variabile "host": "dev.postgres" --> "host": "database"

    Parte 2 - AWS

        creo una istanza EC2 inserendo l'IAM profile della pipeline e lo script nell'UserData
            #!/bin/bash
            sudo apt update
            sudo apt install -y ruby
            cd /home/ubuntu
            wget https://aws-codedeploy-us-east-1.s3.amazonaws.com/latest/install
            sudo chmod +x ./install
            sudo ./install auto
            sudo apt install -y docker.io
            sudo systemctl start docker
            sudo usermod -a -G docker ubuntu
            sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
            sudo chmod +x /usr/local/bin/docker-compose

        creo una nuova pipeline impostando una nuova role --> creo repository su git --> creo una nuova applicazione con CodeDeploy --> creo un nuovo Deployment Group (deselezionando il LoadBalancer) --> creo la pipeline (non funzionante perchè mancano i file di configurazione)

        creo il .gitignore --> C:\Users\user\Desktop\Prima prova DEVO\Prima prova DEVO\.gitignore

        creo un db aws (RDS) --> Postgres --> Free Trial --> UserName: itsuser --> PSW: itsuser01 --> selezione la stessa vpc dell'EC2 creata precedentemente

        cambio nell'oggetto pool "host":"databse" --> "host":"gentilericcardoesamefin.c9nj1x2p6gk5.eu-west-1.rds.amazonaws.com"

        cancello la parte di db nel docker-compose (in questo caso ho commentato per facilitare la prova in locale) e le loro dipendenza (depends_on)







Parte 3 - Sicurezza

<button><a style='color:#FFFFFF' href=http://localhost:8080>HOME</a></button>&nbsp; --> <button><a style='color:#FFFFFF' href=/>HOME</a></button>&nbsp;


