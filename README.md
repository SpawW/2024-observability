# 2024-observability

### Atualize os pacotes do SO

```
sudo apt update -y 

sudo apt upgrade -y
```


# Instalar o Docker

```
curl -fsSL https://get.docker.com -o get-docker.sh

sh get-docker.sh
```

# Habilita o docker para o usuário ubuntu 

```
sudo apt-get install -y uidmap

dockerd-rootless-setuptool.sh install
```

#### Testando o docker 

```
docker run hello-world
```

### Clone o repositório

```
git clone -b install_prometheus https://github.com/SpawW/2024-observability.git

cd 2024-observability

docker compose up -d

```

### Configure o prometheus para buscar informações no rotten potatoes
- Altere o docker-compose.yml para mapear o arquivo prometheus.yml como um volume e adicione as configurações do que coletar
- Adicione o auto monitoramento do prometheus, teste
- Adicione o monitoramento do rotten potatoes, teste
