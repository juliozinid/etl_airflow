🚀 Projeto: ETL Orquestrado com Apache Airflow

📌 Descrição

Este projeto implementa um pipeline de dados automatizado e escalável usando Apache Airflow, PostgreSQL e MongoDB. O objetivo é consolidar informações de acessos ao site (MongoDB) e pedidos de clientes (PostgreSQL) em um Data Warehouse (PostgreSQL) para análise.

🎯 Objetivos do Projeto

✅ Extrair dados de MongoDB e PostgreSQL✅ Transformar os dados, cruzando logs de acesso e pedidos✅ Carregar os dados no Data Warehouse (PostgreSQL)✅ Orquestrar o processo com Apache Airflow✅ Criar um dashboard opcional para análise

🏗 Arquitetura do Projeto

etl_project/
│── dags/                   # DAGs do Airflow
│   ├── etl_pipeline.py     # DAG principal
│── scripts/                # Scripts Python para ETL
│   ├── extract_mongo.py    # Extração do MongoDB
│   ├── extract_postgres.py # Extração do PostgreSQL
│   ├── transform_data.py   # Transformação dos dados
│   ├── load_to_dwh.py      # Carregamento no Data Warehouse
│── configs/                # Configurações do projeto
│   ├── airflow.cfg         # Configuração do Airflow
│   ├── db_config.json      # Configurações de conexão com os bancos
│── tests/                  # Testes automatizados
│   ├── test_extract.py     # Testes de extração
│   ├── test_transform.py   # Testes de transformação
│   ├── test_load.py        # Testes de carga
│── logs/                   # Logs do pipeline
│── dashboards/             # Dashboard para análise de dados
│   ├── dashboard.py        # Aplicação Streamlit para visualização
│── docker/                 # Configuração para rodar em Docker
│   ├── Dockerfile          # Dockerfile para Airflow
│   ├── docker-compose.yml  # Arquivo de configuração do ambiente
│── requirements.txt        # Dependências do projeto
│── README.md               # Documentação do projeto

⚙️ Tecnologias Utilizadas

🔹 Apache Airflow - Orquestração de workflows🔹 PostgreSQL - Banco de dados relacional🔹 MongoDB - Banco NoSQL para logs de acesso🔹 Python (pandas, psycopg2, pymongo) - Scripts de ETL🔹 Docker & Docker Compose - Contêineres para ambiente isolado🔹 Streamlit (opcional) - Dashboard para visualização

🚀 Configuração do Ambiente

1️⃣ Clonar o Repositório

git clone https://github.com/seu-usuario/etl_airflow.git
cd etl_airflow

2️⃣ Criar o Ambiente Docker

cd docker
docker-compose up -d --build

✅ Isso iniciará os containers do Airflow, PostgreSQL e MongoDB.

3️⃣ Acessar o Apache Airflow

🔗 Acesse a interface do Airflow:📌 http://localhost:8080 (Usuário: admin | Senha: admin)

4️⃣ Rodar o Pipeline ETL

No Airflow, ative o DAG etl_pipeline.

Aguarde a execução automática ou acione manualmente.

Monitore os logs para verificar a execução.

🛠 Detalhes do Pipeline ETL

1️⃣ Extração de Dados

📌 MongoDB: Logs de acesso ao site📌 PostgreSQL: Pedidos dos clientes

2️⃣ Transformação

📌 Cruzamento dos dados por user_id📌 Normalização e limpeza dos registros

3️⃣ Carga no Data Warehouse

📌 Salvando os dados transformados no PostgreSQL

📊 Dashboard (Opcional)

Para visualizar os dados transformados, use Streamlit:

cd dashboards
streamlit run dashboard.py

Acesse http://localhost:8501 para ver os insights.

✅ Testes Automatizados

Execute os testes para garantir a qualidade dos scripts:

pytest tests/

📝 Melhorias Futuras

🚀 Adicionar monitoramento com Prometheus/Grafana🚀 Melhorar performance do ETL com batch inserts🚀 Implementar notificações via Slack no Airflow

📌 Conclusão

Este projeto demonstra como criar um pipeline ETL robusto, escalável e automatizado com Apache Airflow e Docker. 🚀

Se tiver dúvidas ou sugestões, abra uma issue ou entre em contato! 😃

