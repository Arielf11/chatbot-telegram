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
