# 🤖 Agente de IA para Gestão de Tarefas no Trello via Chat
[Translate to English](https://github.com/sthefanyalaminos/agent-task-manager/blob/main/README_EN.md)
 
> Automação no n8n que transforma uma conversa simples no chat em atualizações automáticas de cards no Trello.
 
---
Esse projeto nasceu da vontade de simplificar algo que faço todo dia: organizar minhas tarefas. Em vez de abrir o board no Trello e arrastar cards manualmente, criei um agente de IA que conversa comigo, entende o que eu falo sobre o andamento do meu dia e atualiza o board sozinho.
 
Ao iniciar a conversa, o agente cumprimenta o usuário e pergunta quais são as tarefas do dia. A partir daí, basta ir contando o progresso pelo chat: "Comecei a tarefa X", "Terminei a Y", o agente identifica o estágio certo e move o card automaticamente entre:
 
- **A Fazer** - tarefas planejadas
- **Em Andamento** - tarefas em execução
- **Concluído** - tarefas finalizadas

A integração acontece em tempo real: cada atualização informada no chat reflete imediatamente no board do Trello.

## Como funciona
1. O usuário inicia a conversa no chat do n8n.
2. O agente (Google Gemini) cumprimenta e pergunta quais são as tarefas do dia.
3. O usuário relata o andamento de cada atividade em linguagem natural.
4. O agente interpreta a mensagem e identifica qual card e qual novo estágio.
5. Uma requisição HTTP é enviada à API do Trello, movendo o card para a lista correspondente.
6. O Redis mantém o histórico da conversa, dando contexto ao agente entre as interações.

## Tecnologias utilizadas
- **n8n** - Orquestração do workflow
- **Google Gemini (Google AI API)** - Modelo de linguagem do agente
- **Redis** - Memória de conversa (Redis Chat Memory)
- **Trello API** - Leitura e atualização dos cards via HTTP Request

## Arquitetura do workflow
 
```
Chat Trigger (n8n)
      │
      ▼
AI Agent 
      ├── Gemini Chat Model (modelo de linguagem)
      │
      ├── Redis Chat Memory (contexto da conversa)
      │
      └── HTTP Request → Trello API (buscar, criar e mover card entre listas)
```

## Como usar 
1. Importe o arquivo `workflow.json` no seu n8n.
2. Configure as credenciais:
   - **Google AI API Key** (Gemini)
   - **Redis** (host, port e password)
   - **Trello API Key + Token**
3. Ajuste os IDs das listas do Trello (A Fazer, Em Andamento, Concluído) nos nodes de HTTP Request.
4. Ative o workflow e inicie a conversa pelo chat do n8n.

## Autoria
Projeto desenvolvido por Sthefany Alaminos.