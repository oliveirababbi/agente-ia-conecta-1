# 🤖 Projeto: Conecta 1.0

Automação de atendimento via **WhatsApp** utilizando um **agente de IA** que interpreta mensagens, responde de forma contextual e ignora mensagens de grupos ou APIs internas. O objetivo é **reduzir o tempo de resposta e manter uma comunicação automatizada, porém personalizada**.

---

## ⚙️ Visão Geral

A automação foi construída no **n8n** e conecta um **webhook** de mensagens recebidas a um **agente de IA** com modelo **Google Gemini** e **memória armazenada em PostgreSQL**.

Após o processamento, a automação simula ações humanas (marcar como lida, digitar, aguardar) e envia a resposta via **WhatsApp**.

**Tecnologias principais:**
- n8n (automação)
- Waha (integração WhatsApp)
- Google Gemini (IA conversacional)
- PostgreSQL (memória e contexto)
- Easypanel (VPS de hospedagem)

---

## 🔁 Fluxo de Funcionamento

### Etapas principais do workflow

1. **Webhook**
   - Recebe mensagens enviadas ao WhatsApp.
   - Ponto de entrada do fluxo.

2. **Dados (manual)**
   - Registra informações da mensagem (texto, número, horário etc.).
   - Facilita manipulação dentro do fluxo.

3. **Ignorar API**
   - Filtro para mensagens automáticas ou técnicas.

4. **Ignorar Grupos**
   - Processa apenas conversas privadas.

5. **AI Agent**
   - Conecta ao **Google Gemini Chat**.
   - Usa **PostgreSQL Chat Memory** para contexto.
   - Gera respostas conforme histórico e intenção.

6. **Send Seen**
   - Marca a mensagem como visualizada.

7. **Start Typing**
   - Simula digitação humana.

8. **Wait**
   - Adiciona atraso natural antes da resposta.

9. **Send Text Message**
   - Envia a resposta final ao usuário.

---

## 🧩 Componentes e Integrações

| Componente | Função | Tecnologia |
|-------------|--------|-------------|
| Webhook | Entrada de dados | n8n |
| AI Agent | Processamento da linguagem | Google Gemini |
| Memory | Armazenamento de contexto | PostgreSQL |
| Chat Actions | Envio e simulação de mensagens | Waha |
| Hospedagem | VPS para execução do n8n e banco | Easypanel |

---

## 📈 Resultados Esperados

- Reduzir tempo médio de resposta no WhatsApp  
- Classificação automática do tipo de contato  
- Melhorar experiência do usuário com empatia e contexto  
- Registrar histórico de conversas para análises futuras

---

## 🚀 Próximos Passos

- Implementar classificação de intenção mais granular  
- Criar métricas de desempenho (tempo médio, taxa de resolução, satisfação)  
- Integrar com CRM para captura automática de leads  

---

## 🗃️ Configurações Técnicas

### Banco de Dados (PostgreSQL)
- **Host:** interno do VPS (configurado via Easypanel)  
- **Tabelas:** `chat_memory`, `users`, `logs`  
- **Uso:** armazenamento de contexto e histórico das conversas  

### Waha
- **Função:** ponte de comunicação com WhatsApp  
- **Autenticação:** token via header  
- **Ações utilizadas:** sendText, markSeen, startTyping  

---

## Fluxo Visual

<img width="1217" height="399" alt="image" src="https://github.com/user-attachments/assets/20e1d7ec-3fab-4877-9677-d1bc9a8f8fc9" />


---

## Autoria

Desenvolvido por **Barbara Oliveira (Babbi)**  
> Projeto da **IA Connect** — Automação inteligente de atendimento via WhatsApp  
> Hospedado via **Easypanel VPS**
> Saiba mais: https://ia-connect.lovable.app/

---

