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
git clone -b install_grafana https://github.com/SpawW/2024-observability.git

cd 2024-observability

docker compose up -d

```

### Configure o prometheus para buscar informações no rotten potatoes e do docker
- Altere o docker-compose.yml para mapear o arquivo prometheus.yml como um volume e adicione as configurações do que coletar
- Adicione o auto monitoramento do prometheus, teste
- Adicione o monitoramento do rotten potatoes, teste
- Adicione o monitoramento do docker usando o ip EXTERNO

### Altere o deaemon do docker do docker

```
sudo vi /etc/docker/daemon.json

```


```
{
  "metrics-addr" : "0.0.0.0:9323",
  "experimental" : true
}
```

### Reiniciar o docker 

```
sudo systemctl restart docker
```

### Recuperar o IP do contêiner do prometheus

```
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' prometheus
```

### Recuperar o IP do gateway Docker associado ao contêiner

```
docker inspect -f '{{range .NetworkSettings.Networks}}{{.Gateway}}{{end}}' prometheus
```

### Instale o dashboard padrão de prometheus

https://grafana.com/grafana/dashboards/3662-prometheus-2-0-overview/


### Instale o dashboard padrão de docker

https://grafana.com/grafana/dashboards/9621-docker-registry/


### Instale o dashboard padrão do flask
https://github.com/rycus86/prometheus_flask_exporter
