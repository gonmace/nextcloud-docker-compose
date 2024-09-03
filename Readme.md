sudo docker network create --subnet=192.168.192.0/24 ncmagoreal_network
sudo nano /etc/postgresql/<version>/main/pg_hba.conf
host    ncmagoreal    magoreal    192.168.192.4/32    md5
sudo systemctl reload postgresql

sudo docker-compose up -d --remove-orphans

sudo ufw allow 5433/tcp
