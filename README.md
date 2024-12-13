# Sobre o Projeto

#Repositório criado para ingestão de Metadados 

## Pré-requisitos
- Docker
- MySQL

## Instale o Docker
Acesse os procedimentos 1 e 2: https://docs.google.com/document/d/1T5bKzhrKE3-aSW-MeG_RJ7Nr6Jft1Q2KC97_LcpZ9GY/edit?tab=t.0

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

