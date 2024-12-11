# Smart-Garden

## Motivação

O **Smart-Garden** foi desenvolvido para resolver um desafio comum: a falta de conhecimento técnico para cuidar de hortas e plantações. Muitas pessoas não sabem como identificar e corrigir deficiências no solo, o que leva a cultivos pouco produtivos e desistência precoce da prática.

Com o Smart-Garden, é possível monitorar os parâmetros do solo em tempo real e receber recomendações automáticas de fertilizantes, facilitando o cultivo de hortas saudáveis.

---

## Modelagem dos Dados

### **Back-end (Node.js & Express)**

- **Controllers**: Responsáveis por manipular as regras de negócio e processar requisições.
  - `authController.js`
  - `dashboardController.js`
  - `devicesController.js`
  - `eventsController.js`
  - `measuresController.js`

- **Models**: Estrutura de dados e conexão com o banco de dados.
  - `db.js`: Conexão com o banco de dados.
  - `dbTest.js`: Configuração para testes.

- **Routes**: Define os endpoints da API.
  - `authRoutes.js`
  - `dashboardRoutes.js`
  - `devicesRoutes.js`
  - `eventsRoutes.js`
  - `measuresRoutes.js`

- **Testes**: Testes unitários para os controllers.
  - `authController.test.js`
  - `dashboardController.test.js`
  - `devicesController.test.js`
  - `events.test.js`
  - `measures.test.js`

### **Front-end (React)**

- **Componentes**:
  - `Dashboard`
  - `DeviceRegistration`
  - `Events`
  - `LoginScreen`
  - `SideBar`
  - `TopBar`

- **Estilização**:
  - `App.css`
  - `index.css`
  - `styles.css`

### **IA (Python & FastAPI)**

- **Modelos de Recomendação de Fertilizantes**:
  - `fertilizer_classification_model_for_alface.pkl`
  - `fertilizer_recommendation_model.pkl`

- **API Principal**:
  - `main.py`

---

## Arquitetura do Projeto

O **Smart-Garden** utiliza uma arquitetura de três camadas:

1. **Back-end (Node.js & Express)**:
   - Gerencia a lógica de negócio, APIs REST e conexão com o banco de dados.

2. **Front-end (React)**:
   - Interface do usuário desenvolvida em React, com componentes reutilizáveis.

3. **Inteligência Artificial (FastAPI & Python)**:
   - Modelos de IA para recomendar fertilizantes com base nos dados dos sensores.

**Fluxo de dados:**

1. Os sensores enviam dados via **MQTT**.
2. O back-end processa e armazena os dados no banco de dados.
3. A IA analisa os dados e gera recomendações.
4. O front-end exibe os dados e as recomendações em tempo real.

---

## Requisitos do Projeto

### **Autenticação e Controle**
- **RF01**: Autenticação de Usuário
- **RF02**: Controle de Acesso

### **Monitoramento e Dashboard**
- **RF03**: Dashboard de Monitoramento
- **RF06**: Leitura Modbus
- **RF07**: Transmissão via MQTT

### **Gestão de Dados**
- **RF08**: Escuta Contínua de Tópicos MQTT
- **RF09**: Armazenamento de Dados
- **RF10**: APIs REST

### **Eventos e Alertas**
- **RF04**: Gestão de Eventos
- **RF12**: Recomendação de Fertilizantes por IA
- **RF11**: Visualização Interativa

### **Cadastro de Dispositivos**
- **RF05**: Cadastro de Dispositivos

---

## Ferramentas e Dependências

### **Back-end**
- **Node.js & Express**
- **MQTT.js**: Para comunicação MQTT
- **MySQL**: Banco de dados
- **Jest**: Testes unitários

### **Front-end**
- **React**
- **G2Plot**: Para visualização de dados

### **IA**
- **Python & FastAPI**
- **Scikit-Learn**: Modelos de machine learning
- **Pickle**: Para serialização dos modelos

---

## Configurações Necessárias

### **Instalação do Back-end**

```bash
cd smart-garden-backend-main
npm install
npm start
```

### **Instalação do Front-end**

```bash
cd smart-garden-frontend-main
npm install
npm start
```

### **Execução da IA**

```bash
cd smart-garden-ai-main
pip install -r requirements.txt
python main.py
```

---

## Metodologia Utilizada

Foi aplicada a metodologia **Kanban** para organizar as tarefas do projeto. Utilizamos ferramentas como **Trello** para gerenciar o fluxo de trabalho, com colunas:

- **Backlog**: Tarefas planejadas.
- **Em Progresso**: Tarefas em desenvolvimento.
- **Concluído**: Tarefas finalizadas.

Essa abordagem proporcionou visibilidade, flexibilidade e melhor colaboração entre os membros da equipe.

---

## Guia para Novos Desenvolvedores

### **Passos para Começar**

1. **Clone o Repositório**
   ```bash
   git clone <url-do-repositorio>
   ```

2. **Instale as Dependências**
   - Back-end: `npm install`
   - Front-end: `npm install`
   - IA: `pip install -r requirements.txt`

3. **Configure o Banco de Dados**
   - Utilize o MySQL para criar o banco de dados necessário.

4. **Execute os Serviços**
   - **Back-end**: `npm start`
   - **Front-end**: `npm start`
   - **IA**: `python main.py`

5. **Teste a Aplicação**
   - Acesse o front-end em `http://localhost:3000`
   - Verifique a API em `http://localhost:5000`

6. **Contribua**
   - Utilize o quadro Kanban para organizar suas tarefas.

---

**Desenvolvido por:** Equipe Smart-Garden
