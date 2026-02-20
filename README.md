# 🤖 Agente de IA no WhatsApp + Catálogo Digital — Chaveiro Magenta

Automação desenvolvida com n8n que integra um catálogo de produtos estruturado no Notion, indexado em banco vetorial no Supabase, com um agente de IA no WhatsApp — permitindo atendimento automatizado, consulta de produtos e recomendações para clientes.

---

## 🧩 O Problema

A Chaveiro Magenta possuía mais de 230 SKUs sem organização centralizada. O atendimento ao cliente era feito manualmente, com alto volume de perguntas repetitivas sobre produtos, preços e disponibilidade. Não havia conexão entre o estoque, o e-commerce e o canal de atendimento.

---

## 💡 A Solução

Um sistema integrado em quatro camadas:

1. **Notion como fonte de dados** — banco de dados relacional com todos os produtos, categorias, preços e atributos técnicos
2. **Supabase como banco vetorial** — os dados do Notion foram exportados e indexados no Supabase com embeddings, permitindo busca semântica pela IA
3. **Yampi como vitrine** — o catálogo digital do e-commerce alimentado pelos dados estruturados
4. **Agente de IA no WhatsApp via n8n** — atende clientes automaticamente, consulta o Supabase em tempo real e responde com base nos dados vetorizados

> **Por que Supabase e não consulta direta ao Notion?**
> Bancos vetoriais permitem busca semântica — a IA não precisa de uma pergunta exata para encontrar o produto certo. Se o cliente perguntar "tem algo para porta de madeira?", o sistema encontra os produtos relevantes mesmo que essa frase exata não exista no banco.

---

## 🔁 Como o Fluxo Funciona

```
Cliente envia mensagem no WhatsApp
        ↓
n8n recebe via webhook
        ↓
IA interpreta a intenção do cliente
        ↓
Busca semântica no Supabase (banco vetorial)
        ↓
Retorna produtos e informações relevantes
        ↓
Gera resposta personalizada
        ↓
Envia resposta ao cliente no WhatsApp
```

---

## 🛠️ Tecnologias Utilizadas

| Ferramenta | Função |
|------------|--------|
| n8n | Orquestração de todo o fluxo |
| Notion | Estruturação e organização dos dados de produtos |
| Supabase | Banco vetorial com embeddings para busca semântica |
| WhatsApp API | Canal de atendimento |
| OpenAI API | Geração de embeddings e interpretação de linguagem natural |
| Yampi | Plataforma de e-commerce |

---

## 📸 Fluxo no n8n

> 
<img width="1385" height="481" alt="Captura de Tela 2026-02-20 às 14 52 46" src="https://github.com/user-attachments/assets/7075254e-2c5d-45ea-9ed2-64b6fc158a6d" />

---

## 📊 Resultados

- ✅ Lançamento do catálogo digital estruturado em maio de 2025
- ✅ Redução do trabalho manual de atualização de dados de produtos
- ✅ Atendimento automatizado 24h no WhatsApp sem intervenção humana
- ✅ Base escalável para expansão do catálogo e novos fluxos de IA

---


## 🧠 Aprendizados do Projeto

- Estruturação de banco de dados relacional no Notion para servir como origem dos dados
- Indexação de dados em banco vetorial (Supabase + pgvector) com embeddings via OpenAI
- Integração entre múltiplas APIs em um único fluxo n8n
- Uso do nó **HTTP Request** com autenticação por Bearer Token
- Prompt engineering para o agente responder apenas com base nos dados do catálogo

---

## 👤 Autor

**Diego Guimarães Gelman**
[linkedin.com/in/diegogelman](https://linkedin.com/in/diegogelman) · [github.com/diegogelman](https://github.com/diegogelman)
