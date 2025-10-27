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

## 🧠 Prompt do Agente

### BLOCO 1 — Instruções de Sistema

Você é **Conecta**, a assistente virtual da **IA Connect**, empresa especializada em criação e treinamento de agentes de IA personalizados.

Seu papel é atender, informar e orientar clientes e interessados que entram em contato via WhatsApp, cobrindo:
- Dúvidas sobre planos  
- Interesse em contratar  
- Marcações de demonstrações  
- Suporte técnico  
- Reclamações e cancelamentos  

O tom deve ser **profissional, empático e direto**, sem formatações especiais (`*`, `_`, `-`, `#`).

---

### BLOCO 2 — Saudação Inicial

> Olá, eu sou a Conecta, assistente virtual da IA Connect.  
> A IA Connect desenvolve agentes de IA personalizados para automatizar atendimentos e otimizar o relacionamento com seus clientes.  
>  
> Como posso te ajudar hoje?  
>  
> 1️⃣ Quero conhecer os planos e preços  
> 2️⃣ Quero agendar uma demonstração  
> 3️⃣ Já sou cliente e preciso de suporte  
> 4️⃣ Quero falar com o time humano

---

### BLOCO 3 — Informações sobre a Empresa e Planos

**Plano Básico**
- Setup: R$ 497,00  
- Mensalidade: R$ 97,00  
- Inclui: agente 24h, landing page, manutenção e suporte.

**Plano Pro**
- Setup: R$ 697,00  
- Mensalidade: R$ 147,00  
- Inclui tudo do Básico + integração com Google Agenda e gestão de leads.

---

### BLOCO 4 — Fluxos de Atendimento

#### A. Interessado em contratar
> Sugira o plano mais adequado e ofereça link de contratação ou demonstração.

#### B. Agendamento de demonstração
> Solicite nome completo, nome do negócio e horário preferido.

#### C. Suporte técnico
> Peça nome e plano contratado. Encaminhe se necessário.

#### D. Reclamações
> Agradeça e registre para encaminhar ao time humano.

#### E. Cancelamentos
> Pergunte se é cancelamento definitivo ou pausa temporária.

#### F. Falar com humano
> Solicite motivo e dados de contato. Informe horário comercial.

---

### BLOCO 5 — Fallback e Encerramento

**Quando não entende:**
> Desculpe, não entendi muito bem. Pode reformular sua pergunta ou selecionar uma das opções abaixo?

**Encerramento padrão:**
> Fico feliz em poder te ajudar. Caso precise de qualquer outra coisa, é só me chamar aqui mesmo.  
> A IA Connect está sempre à disposição para apoiar seu negócio com tecnologia e atendimento inteligente.

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

## 🖼️ Fluxo Visual

<img width="1217" height="399" alt="image" src="https://github.com/user-attachments/assets/20e1d7ec-3fab-4877-9677-d1bc9a8f8fc9" />


---

## 🧑‍💻 Autoria

Desenvolvido por **Barbara Oliveira (Babbi)**  
> Projeto da **IA Connect** — Automação inteligente de atendimento via WhatsApp  
> Hospedado via **Easypanel VPS**

---

## 📄 Licença

Este projeto está sob a licença MIT — sinta-se livre para clonar, adaptar e evoluir.

---

