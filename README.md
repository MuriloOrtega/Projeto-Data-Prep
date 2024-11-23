# Projeto de Preparação e Transformação de Dados: E-commerce Brasileiro

Este projeto tem como objetivo construir um fluxo completo de preparação e transformação de dados com base em um conjunto de dados de um e-commerce brasileiro. O fluxo extrai dados de um banco de dados relacional e os transforma para análises especializadas, com foco em eficiência e escalabilidade. O resultado final pode ser utilizado para cargas em Data Warehouses ou análises em modelos de **Star Schema** e **Wide Table**.

---

## Tecnologias Utilizadas

- **Docker**: Para containerização do ambiente de desenvolvimento e execução do banco de dados.
- **PostgreSQL**: Banco de dados relacional utilizado para armazenar os dados transacionais.
- **DBeaver**: Ferramenta de administração do banco de dados, permitindo consultas e visualização de dados.
- **Python (Opcional)**: Para realizar tarefas de transformação de dados e orquestrar o fluxo ETL.

---

## Estrutura do Projeto

### 1. Banco de Dados Transacional
Na primeira etapa do projeto, um banco de dados transacional foi criado utilizando os dados do conjunto *Brazilian E-Commerce* disponíveis no Kaggle. Esses dados foram carregados no banco PostgreSQL para permitir análises posteriores.

- **Docker**: O PostgreSQL foi executado em containers Docker para isolar o ambiente de desenvolvimento e garantir que o projeto seja replicável.
- **DBeaver**: Utilizado para administrar o banco de dados PostgreSQL, permitindo a execução de queries e manipulação dos dados.

Você pode acessar o conjunto de dados utilizado neste [link do Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).

---

### 2. Modelagem de Dados

Para análise, dois tipos de modelos foram criados:

- **Star Schema**: Um modelo de banco de dados analítico com tabelas de fatos e dimensões.
- **Wide Table**: Uma tabela ampla que concentra as informações principais em uma única tabela.

Ambos os modelos foram implementados para permitir consultas eficientes e facilitar a análise dos dados.

---

### 3. Fluxo ETL (Extract, Transform, Load)

O fluxo ETL foi projetado para extrair dados brutos, transformá-los conforme a necessidade analítica e carregá-los em um banco de dados de destino.

- **Extração**: Os dados transacionais foram extraídos do banco de dados PostgreSQL.
- **Transformação**: As transformações de dados incluem limpeza, filtragem e agregação, realizadas utilizando Python e SQL.
- **Carregamento**: Os dados transformados foram carregados em um banco de dados analítico, implementando as estruturas **Star Schema** e **Wide Table**.

---

### 4. Abordagem de Tempestividade

O fluxo de transformação foi planejado utilizando uma abordagem de **Batch**. Esta abordagem foi escolhida devido ao volume de dados e à necessidade de realizar transformações periódicas. O uso de **Micro-Batch** ou **Fluxo Contínuo** pode ser considerado no futuro, caso haja necessidade de dados mais atualizados.

---

## Instruções para Execução

### Pré-requisitos

- **Docker**: Certifique-se de ter o Docker instalado em sua máquina. Você pode baixar o Docker [aqui](https://www.docker.com/products/docker-desktop).
- **DBeaver**: Para gerenciar o banco de dados PostgreSQL. Baixe o DBeaver [aqui](https://dbeaver.io/download/).
- **Python (opcional)**: Caso você queira executar scripts Python para transformação de dados. Baixe o Python [aqui](https://www.python.org/downloads/).

### Passos para Execução

1. **Clonar o Repositório**

   Clone este repositório para sua máquina local:
   ```bash
   git clone https://github.com/MuriloOrtega/Projeto-Data-Prep.git
   cd Projeto-Data-Prep
   
2. Configuração do Docker e Banco de Dados

Subir o container do PostgreSQL:
   ```bash            
   docker-compose up -d
````
Acesse o PostgreSQL através do DBeaver utilizando as credenciais configuradas no docker-compose.yml. Importe os dados transacionais do e-commerce.

3. Executando os Scripts Python (Opcional)

Caso você tenha implementado transformações com Python, execute os scripts localmente. Verifique se as dependências estão instaladas:
```bash
   pip install -r requirements.txt
   ```
Execute os scripts Python para realizar a transformação dos dados:
```bash
   python transformacao_dados.py
```
4. Consultas no Banco de Dados

Você pode executar consultas SQL diretamente no DBeaver para visualizar as tabelas de fatos e dimensões.

## Considerações Finais

Este projeto foi desenvolvido com o objetivo de demonstrar como montar um fluxo de transformação de dados utilizando um banco de dados relacional e ferramentas como Docker, DBeaver e Python. A implementação do fluxo ETL visa garantir que os dados brutos sejam preparados e transformados para análises avançadas em modelos de banco de dados analíticos.




   
