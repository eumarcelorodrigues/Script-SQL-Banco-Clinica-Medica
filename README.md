# Script-SQL-Banco-Clinica-Medica


---

# 🏥 Clinica_Cristal - Banco de Dados SQL

## 📌 Sobre o Projeto

Este projeto consiste na modelagem e criação de um banco de dados relacional para gestão de uma clínica médica, com foco em organização, integridade dos dados e escalabilidade.

A estrutura foi desenvolvida utilizando SQL Server e contempla os principais fluxos operacionais de uma clínica: cadastro de pacientes, médicos, convênios, consultas e exames.

---

## 🎯 Objetivo

Criar uma base de dados estruturada que permita:

* Centralizar informações clínicas
* Garantir integridade referencial
* Facilitar consultas e relatórios
* Servir como base para projetos de Business Intelligence (BI)

---

## 🗂️ Estrutura do Banco de Dados

### 📄 Tabela: Convenios

Armazena informações dos convênios médicos.

| Campo       | Tipo          | Descrição           |
| ----------- | ------------- | ------------------- |
| convenio_id | INT (PK)      | Identificador único |
| nome        | NVARCHAR(100) | Nome do convênio    |
| cobertura   | NVARCHAR(200) | Tipo de cobertura   |
| contato     | NVARCHAR(100) | Contato do convênio |

---

### 👤 Tabela: Pacientes

Armazena os dados dos pacientes.

| Campo           | Tipo          | Descrição             |
| --------------- | ------------- | --------------------- |
| paciente_id     | INT (PK)      | Identificador único   |
| nome            | NVARCHAR(100) | Nome do paciente      |
| data_nascimento | DATE          | Data de nascimento    |
| sexo            | CHAR(1)       | Sexo                  |
| telefone        | NVARCHAR(20)  | Telefone              |
| email           | NVARCHAR(100) | Email                 |
| endereco        | NVARCHAR(200) | Endereço              |
| convenio_id     | INT (FK)      | Relação com convênios |

---

### 🩺 Tabela: Medicos

Armazena os dados dos médicos.

| Campo         | Tipo          | Descrição             |
| ------------- | ------------- | --------------------- |
| medico_id     | INT (PK)      | Identificador único   |
| nome          | NVARCHAR(100) | Nome do médico        |
| especialidade | NVARCHAR(100) | Especialidade         |
| CRM           | NVARCHAR(20)  | Registro profissional |
| telefone      | NVARCHAR(20)  | Telefone              |
| email         | NVARCHAR(100) | Email                 |

---

### 📅 Tabela: Consultas

Registra as consultas realizadas.

| Campo         | Tipo     | Descrição           |
| ------------- | -------- | ------------------- |
| consulta_id   | INT (PK) | Identificador único |
| paciente_id   | INT (FK) | Paciente            |
| medico_id     | INT (FK) | Médico              |
| data_consulta | DATE     | Data da consulta    |
| hora_consulta | TIME     | Hora da consulta    |
| motivo        | NVARCHAR | Motivo da consulta  |
| diagnostico   | NVARCHAR | Diagnóstico         |
| receita       | NVARCHAR | Receita médica      |

---

### 🧪 Tabela: Exames

Armazena os exames realizados.

| Campo       | Tipo     | Descrição            |
| ----------- | -------- | -------------------- |
| exame_id    | INT (PK) | Identificador único  |
| paciente_id | INT (FK) | Paciente             |
| consulta_id | INT (FK) | Consulta relacionada |
| medico_id   | INT (FK) | Médico responsável   |
| tipo_exame  | NVARCHAR | Tipo do exame        |
| data_exame  | DATE     | Data do exame        |
| resultado   | NVARCHAR | Resultado do exame   |

---

## 🔗 Relacionamentos

* Pacientes → Convenios (N:1)
* Consultas → Pacientes (N:1)
* Consultas → Medicos (N:1)
* Exames → Pacientes (N:1)
* Exames → Consultas (N:1)
* Exames → Medicos (N:1)

---

## 🧠 Modelagem

O banco foi estruturado seguindo boas práticas de modelagem relacional:

* Uso de **chaves primárias (PK)**
* Uso de **chaves estrangeiras (FK)**
* Garantia de **integridade referencial**
* Estrutura preparada para **normalização**
* Tipos de dados adequados para cada contexto

---

## 🚀 Possibilidades de Uso

Este banco pode ser utilizado para:

* Sistemas de gestão clínica
* Dashboards em Power BI
* Análises de atendimento e produtividade médica
* Controle de histórico de pacientes
* Projetos de portfólio em Data Analytics

---

## 📊 Próximos Passos

* Inserção de dados fictícios para testes
* Criação de queries analíticas
* Integração com ferramentas de BI
* Criação de procedures e views
* Otimização de performance

---

## 💻 Tecnologias Utilizadas

* SQL Server
* T-SQL
* Modelagem de Dados Relacional

---

## 👨‍💻 Autor

**Marcelo Rodrigues**
Especialista em Dados | Business Intelligence | SQL






