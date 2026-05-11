Nola CS Chatbot: Automação de Suporte com IA e n8n

Este projeto foi desenvolvido como uma solução de Customer Success (CS) para a Nola. O objetivo é automatizar o atendimento de primeiro nível, utilizando Inteligência Artificial para consultar uma base de conhecimento dinâmica e registrar logs de auditoria em tempo real.

🚀 Funcionalidades
Atendimento Inteligente: Processamento de linguagem natural para entender dúvidas de clientes.

Base de Conhecimento Dinâmica: Integração com Google Sheets que permite atualizações rápidas pela equipe de CS sem necessidade de código.

Fidelidade de Dados: Configurado com temperatura zero para garantir que a IA não "alucine" e siga estritamente as orientações oficiais.

Logs de Auditoria: Registro automático de cada interação (pergunta, resposta e ID da sessão) para análise de métricas e melhoria contínua.

🛠️ Tecnologias Utilizadas
n8n.io: Orquestrador de fluxo de trabalho (Workflow Automation).

Groq Cloud (Llama 3.1): Modelo de linguagem de baixa latência para processamento das respostas.

Google Sheets API: Utilizado como banco de dados NoSQL para conhecimento e logs.

LangChain: Implementação de agentes de IA com ferramentas específicas (Tools).

📋 Estrutura do Fluxo
Gatilho (Chat Trigger): Recebe a entrada do usuário via interface de chat.

Agente de IA (AI Agent): O "cérebro" que decide quando consultar a planilha.

Memory: Mantém o contexto para perguntas de acompanhamento.

Tool (Google Sheets): Função específica para buscar dados em colunas e linhas da planilha.

Logs (Append Row): Após a resposta, o sistema grava automaticamente os dados em uma aba de monitoramento.

⚙️ Como Replicar este Projeto
Importe o arquivo nola-bot-workflow.json para o seu n8n.

Configure suas credenciais na Groq Cloud e gere uma API Key.

Configure as credenciais do Google Cloud Console (OAuth2) para acesso ao Google Sheets.

No nó do AI Agent, ajuste o System Prompt para definir as regras de negócio do seu bot.

👨‍💻 Autor
Danillo Fontes Carvalho
