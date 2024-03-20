
# Projeto Mensageria ADA
Desenvolver um sistema que detecte possíveis transações bancárias fraudulentas de forma assíncrona, usando análise de dados de transações e armazenamento em cache para acesso rápido a dados usados com frequência. Se uma transação for definida como fraudulenta, deverá ser possível fazer o download de um relatório.

# Definição de fraude
Transações realizadas em locais distantes em um curto período de tempo, no qual não seria fisicamente impossível que o cliente viajasse. Exemplo: Compra em São Paulo e minutos depois no Rio de Janeiro


# Dependências
## DOCKER
### Criar 3 containers conforme abaixo:

Container RabbitMQ:
> docker run -d -p 15672:15672 -p 5672:5672 rabbitmq:3-management

Container Redis:
> docker run -d --name redis-stack -p 6379:6379 -p 8001:8001 redis/redis-stack:latest

Container MinIO:
> docker run -d -p 9000:9000 -p 9001:9001 quay.io/minio/minio server /data --console-address ":9001"

## Python
### Instalar o Python na versão 3.12
### Instalar os Modulos abaixo:
Pika:
> pip install pika

MinIO:
> pip install minio

Redis:
> pip install redis

# Execução:
1 - Copiar os arquivos transações.json, validador.py e producer.py

2 - Subir os cointaners

3 - Executar o arquivo validador.py

4 - Em nova janela, executar o arquivo producer.py

