# 🌱 Smart-Garden

## 📚 Sumário

1. [📝 Resumo](#resumo)
2. [🌟 Motivação](#motivação)
3. [🗄️ Modelagem dos Dados](#modelagem-dos-dados)
4. [🛠️ Arquitetura do Projeto](#arquitetura-do-projeto)
5. [✅ Requisitos do Projeto](#requisitos-do-projeto)
    - [🔒 Autenticação e Controle](#autenticação-e-controle)
    - [📊 Monitoramento e Dashboard](#monitoramento-e-dashboard)
    - [💾 Gestão de Dados](#gestão-de-dados)
    - [⚠️ Eventos e Alertas](#eventos-e-alertas)
    - [📋 Cadastro de Dispositivos](#cadastro-de-dispositivos)
    - [⚙️ Requisitos Não Funcionais](#requisitos-não-funcionais)
6. [🛠️ Ferramentas e Dependências](#ferramentas-e-dependências)
7. [📈 Metodologia Utilizada](#metodologia-utilizada)
8. [⚙️ Configurações Necessárias](#configurações-necessárias)
9. [🚀 Guia para Novos Desenvolvedores](#guia-para-novos-desenvolvedores)

---

## 📝 Resumo

O **Smart-Garden** é uma aplicação que facilita o cultivo saudável de hortas e plantações ao fornecer monitoramento de solo em tempo real e recomendações automáticas de fertilizantes. Ele combina tecnologias de **Node.js**, **React** e **FastAPI** para oferecer uma solução completa, intuitiva e eficiente para o gerenciamento de hortas, utilizando sensores de solo e inteligência artificial para análise de dados e geração de recomendações.

---

## 🌟 Motivação

O **Smart-Garden** foi desenvolvido para resolver um desafio comum: a falta de conhecimento técnico para cuidar de hortas e plantações. Muitas pessoas não sabem como identificar e corrigir deficiências no solo, o que leva a cultivos pouco produtivos e desistência precoce da prática.

**Fatos Relevantes:**
- *"A baixa adoção de práticas de manejo e correção de solo por pequenos produtores é uma das causas de baixa produtividade agrícola."* — **Embrapa: Tecnologias para Agricultura Familiar**
- *"No Brasil, cerca de 30% das perdas alimentares estão associadas a práticas inadequadas de manejo no cultivo."* — **SESI-SP: Alimentação e Desperdício**

O **Smart-Garden** facilita o cultivo saudável ao fornecer monitoramento de solo em tempo real e recomendações automáticas de fertilizantes.

---

## 🗄️ Modelagem dos Dados

### **📊 Diagrama de Banco de Dados**

O projeto utiliza a seguinte modelagem de banco de dados:

![Diagrama de Banco de Dados](./Database%20-%20Diagram.png)

**Tabelas:**
- **`tb_users`**: Armazena informações dos usuários.
- **`tb_devices`**: Contém informações dos dispositivos e sua associação com usuários.
- **`tb_measures`**: Armazena as medições dos sensores.
- **`tb_events`**: Registra eventos e alertas associados aos dispositivos.

Essa modelagem atende aos requisitos do projeto e suporta a estrutura MVC utilizada no back-end.

---

## 🛠️ Arquitetura do Projeto

### **🧩 Estrutura Geral**

1. **Back-end (Node.js & Express)**:
   - APIs REST para gerenciar os dados, autenticação e lógica de negócio.

2. **Front-end (React)**:
   - Interface de usuário com componentes reutilizáveis.

3. **Inteligência Artificial (Python & FastAPI)**:
   - Modelos de IA que processam os dados do solo e fornecem recomendações.

![Diagrama da Arquitetura do Projeto](./Application%20-%20Diagram.jpeg)

**Fluxo de Dados**:
1. Sensores enviam dados via **MQTT**.
2. O back-end processa e armazena os dados.
3. A IA faz recomendações com base nesses dados.
4. O front-end exibe os resultados em dashboards.

---

## ✅ Requisitos do Projeto

### 🔒 **Autenticação e Controle**
- **RF01**: Autenticação de Usuário
- **RF02**: Controle de Acesso

### 📊 **Monitoramento e Dashboard**
- **RF03**: Dashboard de Monitoramento
- **RF06**: Leitura Modbus
- **RF07**: Transmissão via MQTT

### 💾 **Gestão de Dados**
- **RF08**: Escuta Contínua de Tópicos MQTT
- **RF09**: Armazenamento de Dados
- **RF10**: APIs REST

### ⚠️ **Eventos e Alertas**
- **RF04**: Gestão de Eventos
- **RF12**: Recomendação de Fertilizantes por IA
- **RF11**: Visualização Interativa

### 📋 **Cadastro de Dispositivos**
- **RF05**: Cadastro de Dispositivos

### ⚙️ **Requisitos Não Funcionais**

- **RNF01**: O sistema deve ser capaz de processar dados em tempo real com latência mínima.
- **RNF02**: A aplicação deve garantir a segurança dos dados, utilizando criptografia para senhas e informações sensíveis.
- **RNF03**: O sistema deve suportar múltiplos usuários simultaneamente sem perda de desempenho.
- **RNF04**: A interface deve ser intuitiva e de fácil navegação.
- **RNF05**: A aplicação deve ser compatível com os principais navegadores (Chrome, Firefox, Edge).
- **RNF06**: O sistema deve ter alta disponibilidade, com tempo de inatividade mínimo.
- **RNF07**: Os dados devem ser armazenados com redundância para evitar perda de informações.

---
