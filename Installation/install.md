On Redhat or CentOS -

yum install -y yum-utils

yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

yum update

yum install docker-ce (or ee-version)

systemctl enable docker && systemctl start docker

systemctl status docker

On Debian and Ubuntu

app-get install apt-transport-https ca-certificates curl software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

apt-get update

apt-get install docker-ce (it enables and starts docker also)

systemctl status docker

Add your user to docker group so that you can run docker commands. The /var/run/docker.sock is where docker runs and is owned by root. 
root is in docker group so any user in docker group can run docker commands

usermod -aG docker <user>

docker ps
