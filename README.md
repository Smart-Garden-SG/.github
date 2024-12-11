# Smart-Garden

## Motivação

O **Smart-Garden** foi desenvolvido para resolver um desafio comum: a falta de conhecimento técnico para cuidar de hortas e plantações. Muitas pessoas não sabem como identificar e corrigir deficiências no solo, o que leva a cultivos pouco produtivos e desistência precoce da prática.

**Fatos Relevantes:**
- *"A baixa adoção de práticas de manejo e correção de solo por pequenos produtores é uma das causas de baixa produtividade agrícola."* — **Embrapa: Tecnologias para Agricultura Familiar**
- *"No Brasil, cerca de 30% das perdas alimentares estão associadas a práticas inadequadas de manejo no cultivo."* — **SESI-SP: Alimentação e Desperdício**

O **Smart-Garden** facilita o cultivo saudável ao fornecer monitoramento de solo em tempo real e recomendações automáticas de fertilizantes.

---

## Modelagem dos Dados

### **Back-end (Node.js & Express)**

- **Controllers**: Controlam as regras de negócio e processamento das requisições:
  - `authController.js`
  - `dashboardController.js`
  - `devicesController.js`
  - `eventsController.js`
  - `measuresController.js`

- **Models**: Estrutura de dados e conexão com o banco de dados:
  - `db.js`: Conexão com o banco de dados.
  - `dbTest.js`: Configuração para testes.

- **Routes**: Define os endpoints da API:
  - `authRoutes.js`
  - `dashboardRoutes.js`
  - `devicesRoutes.js`
  - `eventsRoutes.js`
  - `measuresRoutes.js`

- **Testes**: Arquivos de teste para os controllers:
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

- **Modelos de Recomendações**:
  - `fertilizer_classification_model_for_alface.pkl`
  - `fertilizer_recommendation_model.pkl`

- **API Principal**:
  - `main.py`

### **Diagrama de Banco de Dados**

O projeto utiliza a seguinte modelagem de banco de dados:

![Diagrama de Banco de Dados](path/to/Database-Diagram.png)

**Tabelas:**
- **`tb_users`**: Armazena informações dos usuários.
- **`tb_devices`**: Contém informações dos dispositivos e sua associação com usuários.
- **`tb_measures`**: Armazena as medições dos sensores.
- **`tb_events`**: Registra eventos e alertas associados aos dispositivos.

Essa modelagem atende aos requisitos do projeto e suporta a estrutura MVC utilizada no back-end.

---

## Arquitetura do Projeto

### **Estrutura Geral**

1. **Back-end (Node.js & Express)**:
   - APIs REST para gerenciar os dados, autenticação e lógica de negócio.

2. **Front-end (React)**:
   - Interface de usuário com componentes reutilizáveis.

3. **Inteligência Artificial (Python & FastAPI)**:
   - Modelos de IA que processam os dados do solo e fornecem recomendações.

**Fluxo de Dados**:
1. Sensores enviam dados via **MQTT**.
2. O back-end processa e armazena os dados.
3. A IA faz recomendações com base nesses dados.
4. O front-end exibe os resultados em dashboards.

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
- **Node.js** & **Express**
- **MySQL**
- **MQTT.js**
- **Jest** (para testes)

### **Front-end**
- **React**
- **G2Plot** (para gráficos)

### **IA**
- **Python** & **FastAPI**
- **Scikit-Learn**
- **Pickle** (para modelos)

---

## Configurações Necessárias

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

## Metodologia Utilizada

Utilizamos a metodologia **Kanban** para gerenciar as tarefas do projeto:

- **Colunas do Kanban**:
  - **Backlog**: Tarefas planejadas.
  - **Em Progresso**: Tarefas em desenvolvimento.
  - **Concluído**: Tarefas finalizadas.

Ferramenta utilizada: **Trello**.

---

## Guia para Novos Desenvolvedores

### **Passos para Começar**

1. **Clone o Repositório**:
   ```bash
   git clone <url-do-repositorio>
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
6. **Teste a API** em `http://localhost:5000`.

**Contribua** organizando suas tarefas pelo quadro Kanban.
