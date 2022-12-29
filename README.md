t3.large - ec2 ami

sudo amazon-linux-extras install java-openjdk11 -y

yum install git docker maven tree -y

systemctl enable docker

systemctl restart docker

git clone https://github.com/rajulucky812/jenkins-nexus.git

sudo curl -L "https://github.com/docker/compose/releases/download/1.29.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose


cd jenkins-nexus/

docker-compose up

docker volume create --name=jenkins_home

docker volume create --name=nexus_data

docker-compose up -d

docker-compose up -d
