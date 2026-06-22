# 📊 Analytics Engineering Pipeline com dbt Cloud e PostgreSQL

Pipeline analítico construído com **dbt Core**, **dbt Cloud** e **PostgreSQL**, aplicando conceitos modernos de Analytics Engineering, modelagem de dados e transformação em camadas.

Este projeto demonstra na prática conceitos de Engenharia de Dados, como ingestão, transformação, documentação e governança de dados utilizando uma arquitetura analítica baseada em Landing, Staging, Intermediate e Marts.

---

# 🎯 Objetivo

Construir um pipeline analítico completo utilizando PostgreSQL e dbt, transformando dados operacionais em informações confiáveis para consumo por dashboards, relatórios e análises de negócio.

---

# 🚀 Tecnologias Utilizadas

- Python
- PostgreSQL
- AWS RDS
- dbt Core
- dbt Cloud
- SQL
- Git
- GitHub
- VS Code
- DBeaver

---

# 📦 Arquitetura do Pipeline

O projeto segue uma arquitetura em camadas amplamente utilizada em Analytics Engineering.

```text
PostgreSQL
│
├── public (Fonte Transacional Simulada)
│
▼
Landing (Dados Brutos)
│
▼
Staging (Limpeza e Padronização)
│
▼
Intermediate (Regras de Negócio)
│
▼
Marts (Dados Analíticos)
│
▼
Dashboards / Relatórios
```

---

# 📖 Entendendo as Camadas

## 🐘 PostgreSQL (Fonte Transacional)

O schema `public` simula um ambiente transacional contendo os dados operacionais utilizados como entrada para o pipeline.

Exemplos:

- customers
- products
- sales
- refunds

---

## 📥 Landing (Dados Brutos)

Primeira camada do pipeline.

Responsável por armazenar uma cópia dos dados provenientes da origem sem alterações significativas.

Objetivos:

- Preservar dados originais
- Garantir rastreabilidade
- Facilitar auditorias

Exemplo:

```text
public.sales
      │
      ▼
landing.sales
```

---

## 🧹 Staging (Limpeza e Padronização)

Responsável pela preparação dos dados para análise.

Nesta camada os modelos são materializados como **Views**, seguindo boas práticas do dbt.

Exemplos:

```text
stg_clientes
stg_produtos
stg_vendas
stg_estorno
```

Transformações realizadas:

- Padronização de nomes
- Conversão de tipos
- Tratamento de nulos
- Correção de inconsistências

Exemplo:

Antes:

```sql
NomeCliente
```

Depois:

```sql
nome_cliente
```

---

## ⚙️ Intermediate (Regras de Negócio)

Camada responsável pela consolidação das informações e aplicação de regras de negócio.

Exemplos:

```text
int_vendas_clientes
int_metricas_vendas
```

Principais atividades:

- JOIN entre tabelas
- Criação de métricas
- Consolidação de dados
- Aplicação de regras de negócio

---

## 📊 Marts (Consumo Analítico)

Camada final do pipeline.

Responsável por disponibilizar dados prontos para consumo analítico.

Exemplos:

```text
mart_vendas
mart_clientes
mart_produtos
```

Consumidores:

- Power BI
- Excel
- Tableau
- Analistas de Dados
- Cientistas de Dados

---

# ☁️ Arquitetura das Ferramentas

```text
VS Code
   │
   ▼
Git
   │
   ▼
GitHub
   │
   ▼
dbt Cloud
   │
   ▼
PostgreSQL (AWS RDS)
```

Fluxo do projeto:

1. Desenvolvimento dos modelos no VS Code.
2. Versionamento através do Git.
3. Publicação no GitHub.
4. Integração automática com dbt Cloud.
5. Execução das transformações no PostgreSQL.
6. Geração automática de documentação e Data Lineage.

---

# 📂 Estrutura do Projeto

```text
projeto-shoesbr/
│
├── analyses/
├── docs/
├── logs/
├── macros/
│
├── models/
│   ├── staging/
│   ├── intermediate/
│   └── marts/
│
├── seeds/
├── snapshots/
├── tests/
│
├── target/
│
├── dbt_project.yml
├── README.md
└── .gitignore
```

---

# 🔍 Qualidade dos Dados

O projeto utiliza testes nativos do dbt para validação dos dados.

Testes aplicados:

- Not Null
- Unique
- Relationships

Benefícios:

- Maior confiabilidade dos dados
- Identificação precoce de falhas
- Garantia da qualidade analítica

---

# 📖 Documentação Automatizada

O dbt permite gerar documentação automaticamente a partir dos modelos e arquivos YAML.

Comandos utilizados:

```bash
dbt docs generate
```

```bash
dbt docs serve
```

A documentação inclui:

- Modelos
- Colunas
- Dependências
- Descrições
- Data Lineage

---

# 🔗 Data Lineage

Uma das principais funcionalidades do dbt é a visualização automática da linhagem dos dados.

Exemplo:

```text
public.sales
      │
      ▼
landing.sales
      │
      ▼
stg_vendas
      │
      ▼
int_metricas_vendas
      │
      ▼
mart_vendas
```

Benefícios:

- Governança
- Rastreabilidade
- Análise de impacto
- Facilidade de manutenção

---

# 📚 Conceitos Aplicados

- Analytics Engineering
- Engenharia de Dados
- PostgreSQL
- SQL
- dbt Core
- dbt Cloud
- AWS RDS
- Data Modeling
- Data Lineage
- Data Quality
- Data Governance
- Git/GitHub

---

# 🎓 Aprendizados

Durante o desenvolvimento deste projeto foram praticados conceitos amplamente utilizados em ambientes corporativos:

- Construção de pipelines analíticos
- Modelagem de dados com dbt
- Integração GitHub + dbt Cloud
- Organização de modelos em camadas
- Testes automatizados
- Governança de dados
- Documentação técnica
- Versionamento de projetos de dados

---

# 📌 Conclusão

Este projeto demonstra a construção de um pipeline analítico moderno utilizando PostgreSQL, dbt Core e dbt Cloud, aplicando boas práticas de Analytics Engineering para transformar dados operacionais em informações confiáveis e prontas para consumo analítico.

A arquitetura em camadas (Landing → Staging → Intermediate → Marts) proporciona organização, escalabilidade, reutilização de código e governança dos dados, simulando um ambiente próximo ao encontrado em empresas orientadas por dados.

---

## ⭐ Principais Diferenciais

✅ PostgreSQL hospedado na AWS RDS

✅ Integração GitHub + dbt Cloud

✅ Arquitetura em camadas

✅ Testes automatizados com dbt

✅ Data Lineage

✅ Documentação automatizada

✅ Boas práticas de Analytics Engineering

✅ Organização seguindo padrões de mercado
