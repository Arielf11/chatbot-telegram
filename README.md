**Desafio - Chatbot clima**

Chatbot desenvolvido no N8N integrado ao Telegram que consulta a temperatura atual de qualquer cidade do Brasil utilizando a API OpenWeather.

O usuário envia uma mensagem para o bot no formato:

São Paulo,SP,BR

O chatbot consulta a API OpenWeather e retorna:
🌤️ A temperatura em São Paulo é de 25°C.

Caso a cidade não seja encontrada:
❌ Cidade não encontrada. Use o formato Cidade,UF,BR (ex.: São Paulo,SP,BR).

**Tecnologias**
N8N
Telegram Bot API
OpenWeather API

**Estrutura do Workflow**

Telegram Trigger
→ Set Queue
→ Normalize Input
→ HTTP Request (OpenWeather)
→ IF

Fluxo de sucesso:
→ Format Success
→ Telegram Send Message

Fluxo de erro:
→ Telegram Error

**Variáveis de Ambiente**

**Configure as seguintes variáveis no N8N:**

**OPENWEATHER_API_KEY**=sua_chave_openweather

**TELEGRAM_BOT_TOKEN**=seu_token_telegram

**Como obter a chave OpenWeather**
Criar conta em https://openweathermap.org
Acessar API Keys
Criar uma chave
Inserir o valor na variável: **OPENWEATHER_API_KEY**

Como criar o Bot Telegram
Abrir @BotFather
Executar o comando: /newbot
Copiar o token gerado(HTTP API)

**Como importar o Workflow**
Abrir o N8N
Selecionar Import Workflow
Escolher o arquivo: **workflow-chatbot-telegram.json**
Configurar as credenciais do Telegram
Salvar
Ativar o workflow


**Testes Recomendados**

**Teste 1**
**Entrada:**
Belo Horizonte,MG

**Saída esperada:**
🌤️ A temperatura em Belo Horizonte é de XX°C.

**Teste 2**
**Entrada:**
Rio de Janeiro,RJ

**Saída esperada:**
🌤️ A temperatura em Rio de Janeiro é de XX°C.

**Teste 3**
**Entrada:**
Curitiba,PR,

**Saída esperada:**
🌤️ A temperatura em Curitiba é de XX°C.

**Teste de Erro**

**Entrada:**
CidadeInexistente,XX,BR

**Saída esperada:
**❌ Cidade não encontrada. Use o formato Cidade,UF,BR (ex.: São Paulo,SP,BR).
