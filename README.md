# Nola CS Chatbot: Automação de Suporte com IA e n8n

Este projeto foi desenvolvido como uma solução de **Customer Success (CS)** para a empresa **Nola**. O objetivo é automatizar o atendimento de primeiro nível, utilizando Inteligência Artificial para consultar uma base de conhecimento dinâmica e registrar logs de auditoria em tempo real.

---

## Funcionalidades

* **Atendimento Inteligente:** Processamento de linguagem natural para entender e resolver dúvidas de clientes.
* **Base de Conhecimento Dinâmica:** Integração com Google Sheets que permite atualizações rápidas pela equipe de CS sem necessidade de alteração no fluxo.
* **Fidelidade Total:** Configurado com *Temperature 0* e comandos de sistema rígidos para garantir que a IA replique exatamente as informações oficiais, sem alucinações.
* **Logs de Auditoria:** Registro automático de cada interação (data, pergunta, resposta e ID da sessão) para monitoramento de métricas.

---

## Tecnologias Utilizadas

* **n8n.io:** Orquestrador de workflow e automação de processos.
* **Groq Cloud (Llama 3.1):** LLM de alta performance e baixa latência.
* **Google Sheets API:** Utilizado como banco de dados para conhecimento e repositório de logs.
* **LangChain:** Framework para gerenciamento do agente de IA e ferramentas (*Tools*).

---

## Segurança e Configuração (Importante)

Para fins de portfólio e proteção de dados sensíveis, o arquivo `workflow.json` disponível neste repositório foi **anonimizado**.

### Campos alterados por segurança:

* **`documentId`**: Removido o ID original da planilha do Google.
* **`credentials`**: Os IDs de credenciais (Google e Groq) foram substituídos por placeholders.
* **`instanceId` / `webhookId`**: Removidos identificadores únicos da instância do n8n.

### Como configurar o seu:

1. **Importe** o arquivo JSON no seu n8n.
2. **Crie suas credenciais** para a Groq API e Google Sheets OAuth2 nos nós correspondentes.
3. **Substitua o ID da Planilha** nos nós "Google Sheets Tool" e "Append row in sheet" pelo ID da sua própria planilha.
4. Certifique-se de que sua planilha possui as abas e colunas conforme configurado nos campos de mapeamento.

---

## Estrutura do Fluxo

1. **Gatilho (Chat Trigger):** Recebe a entrada do usuário via interface de chat.
2. **Agente de IA (AI Agent):** O núcleo lógico que decide quando consultar a ferramenta.
    * **Memory:** Mantém o contexto para perguntas sequenciais.
    * **Tool (Sheets):** Busca respostas específicas na base de dados.
3. **Saída de Dados (Logs):** Grava a interação final na aba de monitoramento do Google Sheets.

---

### Autor

Danillo F Carvalho
