# 2024-observability

### Atualize os pacotes do SO
sudo apt update -y 
sudo apt upgrade -y

# Instalar o Docker
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh

# Habilita o docker para o usuário ubuntu 
sudo apt-get install -y uidmap
dockerd-rootless-setuptool.sh install

# Testando o docker 
docker run hello-world

### Clone o repositório
```
git clone git@github.com:SpawW/2024-observability.git
```
