# Agente IA de Gerenciamento de Tarefas com Trello
 
> Projeto desenvolvido como parte do desafio do Bootcamp CI&T – Do Prompt ao Agente, realizado pela DIO. O objetivo é construir um agente de IA conversacional que automatiza o gerenciamento de tarefas no Trello, integrando Python com a API do Trello e o Google ADK.
 
---
## Sobre o Projeto
 
Este projeto cria um **agente de inteligência artificial** capaz de gerenciar o dia a dia de trabalho através de uma conversa simples no terminal. Ao ser iniciado, o agente faz uma saudação personalizada com a data atual e pergunta quais são as tarefas do dia. A partir daí, o usuário pode informar o andamento de cada atividade pelo chat, e o agente atualiza automaticamente os cards no quadro do Trello, movendo-os entre os estágios:
 
- **A Fazer** — tarefas planejadas
- **Em Andamento** — tarefas em execução
- **Concluído** — tarefas finalizadas
A integração acontece em tempo real: cada atualização informada no chat reflete imediatamente no board do Trello.
 
---
## Tecnologias Utilizadas
 
- **Python** - linguagem principal do projeto
- **Google ADK** - framework para construção do agente de IA
- **py-trello** - biblioteca Python para integração com a API do Trello
- **python-dotenv** - gerenciamento de variáveis de ambiente
---
 
## Pré-requisitos
 
Antes de rodar o projeto, você precisa ter:
 
- Python 3.7 ou superior instalado
- Uma conta ativa no [Trello](https://trello.com/)
- pip (gerenciador de pacotes Python)
- Um quadro criado no Trello com as listas: **A Fazer**, **Em Andamento** e **Concluído**
---
 
## Configuração do Ambiente
 
### 1. Clone o repositório
 
```bash
git clone https://github.com/sthefanyalaminos/agent-task-manager.git
cd agent-task-manager
```
 
### 2. Instale as dependências
 
```bash
pip install -r requirements.txt
```
 
O arquivo `requirements.txt` inclui:
 
```
google-adk
py-trello
datetime
python-dotenv
```
 
### 3. Configure as credenciais do Trello
 
Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis:
 
```env
TRELLO_API_KEY=sua_api_key_aqui
TRELLO_TOKEN=seu_token_aqui
TRELLO_BOARD_ID=id_do_seu_quadro
```
 
> ⚠️ Nunca suba o arquivo `.env` para o GitHub. Certifique-se de que ele está no `.gitignore`.
 
---
## Como Obter as Credenciais do Trello
 
### Passo 1 - Criar um Power-Up (Aplicativo)
 
1. Acesse o [portal de Power-Ups do Trello](https://trello.com/power-ups/admin/)
2. Clique em **"New"** para criar um novo aplicativo
3. Preencha o nome, workspace e e-mail de contato
4. Clique em **"Criar"**
### Passo 2 - Obter a API Key
 
Na página do seu Power-Up, copie a **API Key** exibida na seção "API Key".
 
### Passo 3 - Gerar o Token de Autorização
 
Monte a URL abaixo substituindo `SUA_API_KEY`:
 
```
https://trello.com/1/authorize?expiration=never&name=AppDio&scope=read,write&response_type=token&key=SUA_API_KEY
```
 
Acesse essa URL no navegador, revise as permissões e clique em **"Permitir"**. O token será exibido na tela - copie e guarde com segurança.
 
> 📖 Guia completo de configuração: [agents/agent04/readme.md](./agents/agent04/readme.md)
 
---
 
## Como Executar
 
```bash
python agents/agent04/agent.py
```
 
Ao iniciar, o agente irá:
 
1. Cumprimentar com a data atual
2. Perguntar quais são as tarefas do dia
3. Criar os cards no Trello automaticamente
4. Aguardar atualizações de status via chat e mover os cards em tempo real
---
 
## O que aprendi com este projeto
 
- Como integrar Python com APIs externas usando bibliotecas de terceiros (`py-trello`)
- Como configurar e usar o **Google ADK** para construir agentes de IA conversacionais
- A importância do gerenciamento seguro de credenciais com variáveis de ambiente (`.env`)
- Como estruturar um projeto Python com múltiplos agentes e separação de responsabilidades
- Na prática: Com poucas linhas de Python, já é possível ter um assistente funcional integrado a ferramentas do dia a dia
---

## Autoria
Desenvolvido por Sthefany Alaminos, durante o Bootcamp CI&T – Do Prompt ao Agente, realizado pela DIO.
