# 🌱 Smart-Garden

## 📚 Sumário

1. [🌟 Motivação](#motivação)
2. [🗄️ Modelagem dos Dados](#modelagem-dos-dados)
3. [🛠️ Arquitetura do Projeto](#arquitetura-do-projeto)
4. [✅ Requisitos do Projeto](#requisitos-do-projeto)
    - [🔒 Autenticação e Controle](#autenticação-e-controle)
    - [📊 Monitoramento e Dashboard](#monitoramento-e-dashboard)
    - [💾 Gestão de Dados](#gestão-de-dados)
    - [⚠️ Eventos e Alertas](#eventos-e-alertas)
    - [📋 Cadastro de Dispositivos](#cadastro-de-dispositivos)
    - [⚙️ Requisitos Não Funcionais](#requisitos-não-funcionais)
5. [🛠️ Ferramentas e Dependências](#ferramentas-e-dependências)
6. [📈 Metodologia Utilizada](#metodologia-utilizada)
7. [⚙️ Configurações Necessárias](#configurações-necessárias)
8. [🚀 Guia para Novos Desenvolvedores](#guia-para-novos-desenvolvedores)

---

## 📝 Resumo

O **Smart-Garden** é uma aplicação web e de inteligência artificial que facilita o cultivo saudável de hortas e plantações ao fornecer monitoramento de solo em tempo real e recomendações automáticas de fertilizantes. Ele combina tecnologias de **Aplicação WEB** e **IA** para oferecer uma solução completa, intuitiva e eficiente para o gerenciamento de hortas, utilizando sensores de solo e inteligência artificial para análise de dados e geração de recomendações.

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
- **`tb_devices`**: Contém informações dos dispositivos.
- **`tb_measures`**: Armazena as medições dos sensores.
- **`tb_events`**: Registra eventos de recomendação e alertas associados aos valores de solo.

---

## 🛠️ Arquitetura do Projeto

### **🧩 Estrutura Geral**

1. **Back-end (Node.js & Express)**:
   - APIs REST para gerenciar os dados, autenticação e lógica de negócio.

2. **Front-end (React)**:
   - Interface de usuário para vizualição das amostras e eventos Gerados pela IA.

3. **Inteligência Artificial (Python & FastAPI)**:
   - Modelos de IA que processam os dados do solo e fornecem recomendações.

![Diagrama da Arquitetura do Projeto](./Application%20-%20Diagram.jpeg)

## **Fluxo de Dados**

1. **Sensores de solo** coletam dados dos parâmetros ambientais.  
2. **Sensores enviam** os dados via Pub **MQTT** para o back-end.  
3. O **back-end processa e armazena** os dados na tabela `tb_measures` do banco de dados **MySQL**.  
4. O **front-end solicita recomendações** de fertilizantes à API de IA desenvolvida com **FastAPI**.  
5. A **IA faz predições** com o modelo **CatBoost** utilizando os dados do solo e climáticos.  
6. O **back-end armazena** a recomendação na tabela `tb_events`.  
7. O **front-end exibe** os dados e as recomendações em dashboards e na tela de eventos.  

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

## 🛠️ Ferramentas e Dependências

### **Back-end**
- **Node.js** & **Express**
- **MySQL**
- **MQTT.js**
- **Jest** (para testes)

### **Front-end**
- **React**
- **G2Plot** (para gráficos)

### **IA**
- **Python** & **FastAPI**
- **PyCaret**

---

## 📈 Metodologia Utilizada

Utilizamos a metodologia **Kanban** para gerenciar as tarefas do projeto:

- **Colunas do Kanban**:
  - **Backlog**: Tarefas planejadas.
  - **Em Progresso**: Tarefas em desenvolvimento.
  - **Concluído**: Tarefas finalizadas.

Ferramenta utilizada: **Trello**.

---

## ⚙️ Configurações Necessárias

### **Back-end**
```bash
cd smart-garden-backend-main
npm install
npm start
```

### **Front-end**
```bash
cd smart-garden-frontend-main
npm install
npm start
```

### **IA**
```bash
cd smart-garden-ai-main
pip install -r requirements.txt
python main.py
```

---

## 🚀 Guia para Novos Desenvolvedores

### **Passos para Começar**

1. **Clone o Repositório**:
   ```bash
   git clone https://github.com/Smart-Garden-SG/smart-garden-backend
   git clone https://github.com/Smart-Garden-SG/smart-garden-frontend
   git clone https://github.com/Smart-Garden-SG/smart-garden-ai
   ```

2. **Instale as Dependências**:
   - Back-end: `npm install`
   - Front-end: `npm install`
   - IA: `pip install -r requirements.txt`

3. **Configure o Banco de Dados**:
   - Utilize MySQL para configurar o banco de dados necessário.

4. **Execute os Serviços**:
   ```bash
   # Back-end
   npm start
   
   # Front-end
   npm start

   # IA
   python main.py
   ```

5. **Acesse o Front-end** em `http://localhost:3000`.

---

## 🤖 Inteligência Artificial no Smart-Garden

### 🌾 Como o CatBoost Recomenda Fertilizantes

### 🧪 **Etapas da Recomendação**

1. **Coleta dos Dados**:  
   - Sensores de solo medem os seguintes parâmetros:  
     - **Nitrogênio (mg/kg)**  
     - **Fósforo (mg/kg)**  
     - **Potássio (mg/kg)**  
     - **pH**  
     - **Condutividade elétrica**  
     - **Temperatura do solo (°C)**  
     - **Umidade (%RH)**  
     - **Salinidade (mg/L)**  
     - **Sólidos Totais Dissolvidos (TDS) (mg/L)**  
   - Dados climáticos fornecidos pela API da **OpenWeather**:  
     - **Temperatura ambiente (°C)**  
     - **Umidade do ar (%)**  
     - **Pressão atmosférica (hPa)**  

2. **Armazenamento**:  
   Os dados coletados são armazenados no banco de dados na tabela `tb_measures`.

3. **Entrada na Tela de Recomendações**:  
   Quando o usuário acessa a tela de recomendações, a aplicação web faz uma requisição para a **API de IA** desenvolvida com **FastAPI**.

4. **Predição com o CatBoost**:  
   O modelo **CatBoost** é carregado e processa os dados recebidos. O modelo foi treinado para identificar quais características do solo estão fora dos padrões ideais para o cultivo de alface.

5. **Lógica de Decisão**:  
   O **CatBoost** avalia os seguintes parâmetros:  
   - **Níveis de Nutrientes**:  
     - **Nitrogênio** baixo → Recomenda **Nitrato de Amônio (NH₄NO₃)**  
     - **Fósforo** baixo → Recomenda **Superfosfato Simples**  
     - **Potássio** baixo → Recomenda **Cloreto de Potássio (KCl)**  
   - **pH do Solo**:  
     - **pH < 6.0** → Recomenda **Enxofre Elementar** para acidificar o solo.  
     - **pH > 7.0** → Recomenda **Calcário** para corrigir a alcalinidade.  
   - **Parâmetros Gerais**:  
     - Se os níveis estão equilibrados → Recomenda **Fertilizante Completo (NPK)**.  

6. **Geração da Recomendação**:  
   - A IA gera a recomendação do fertilizante apropriado.  
   - Um novo evento é inserido na tabela `tb_events` com a recomendação gerada.

7. **Visualização na Interface**:  
   - A recomendação é exibida na tela de eventos da aplicação web para que o usuário possa agir de acordo com a necessidade do solo.

---

### 🔄 **Exemplo de Funcionamento**

**Dados de Entrada**:  
```plaintext
Nitrogênio: 20 mg/kg  
Fósforo: 10 mg/kg  
Potássio: 80 mg/kg  
pH: 5.5  
Condutividade: 2.89 µS/cm  
Temperatura do Solo: 28.43 °C  
Umidade: 52.27 %RH  
Salinidade: 93.12 mg/L  
TDS: 415.67 mg/L  
Fator de Condutividade: 2.47  
Fator de Salinidade: 9.85  
Sensação Térmica: 32.55 °C  
Temperatura: 30.45 °C  
Temperatura Mínima: 22.99 °C  
Temperatura Máxima: 35.25 °C  
Pressão: 1005.52 hPa  
Umidade Relativa: 58.37 %  
```

**Predição do CatBoost**:  
- O modelo identifica que o nível de **nitrogênio** está baixo e o **pH** está ácido.

**Recomendação**:  
- **Nitrato de Amônio (NH₄NO₃)** para corrigir o nível de nitrogênio.  
- **Enxofre Elementar** para ajustar o pH.

---

### 📝 **Resumo do Processo**

1. **Entrada**: Dados do solo e clima.  
2. **Processamento**: O **CatBoost** analisa os dados e identifica deficiências no solo.  
3. **Recomendação**: O fertilizante adequado é sugerido com base nas deficiências detectadas.  
4. **Saída**: A recomendação é armazenada em `tb_events` e exibida na interface da aplicação.

---
