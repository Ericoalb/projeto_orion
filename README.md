# Sobre o Projeto

Repositório criado para servir como uma pequana documentação da sobre a ingestão de MetaDados na plataforma OpenMetada, como tabmém a utilização do Trino como método de consulta. Tudo isso atraves da conteinirização via Docker.

## Pré-requisitos
- Docker
- MySQL

## Instale o Docker
Acesse os procedimentos 1 e 2: https://docs.google.com/document/d/1T5bKzhrKE3-aSW-MeG_RJ7Nr6Jft1Q2KC97_LcpZ9GY/edit?tab=t.0

## Instale o  MySQL
sudo apt update
sudo apt isntall mysql-server

## Executes os Comandos
1. Clone o repositório:
   ```bash
   git clone https://github.com/Ericoalb/projeto_orion.git
   cd projeto_orion
   docker compose -f docker-compose.yml up --detach
## Entre no bash do Trino
docker exec -iti trino bash
## Navegue até o Diretório
cd /etc/trino/catalog
## Atualize o Catalog
printf "connector.name=mysql\nconnection-url=jdbc:mysql://host.docker.internal:3306\nconnection-user=root\nconnectionpassword=12" > mysql.properties

## Verifique se os serviços:
   OpenMetadata: http://localhost:8585
   Airflow: http://localhost:8080

