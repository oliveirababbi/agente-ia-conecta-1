# Conecta 1.0 — Agente de IA (IA Connect)

Automação de atendimento via WhatsApp usando um agente de IA chamado "Conecta".
Fluxos orquestrados com n8n, hospedados em VPS (EasyPanel). Modelo de geração de respostas via LLM (Google Gemini).

## Visão geral
- Plataforma de orquestração: n8n
- Hospedagem: VPS EasyPanel
- Memória / persistência: PostgreSQL
- Prompt base: stored in /prompts/system_prompt.txt

## Estrutura do repositório
- `/n8n` — export do fluxo e instruções para importar
- `/prompts` — prompts e instruções do agente (BLOCO 1–5)
- `/infra` — scripts 
- `/docs` — documentação técnica, runbooks e arquitetura
- `/src` — scripts de apoio e utilitários


