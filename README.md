# 🧬 Resumidor de Artigos Científicos (PubMed) com IA

Automação que recebe um link de artigo do PubMed e devolve um resumo 
estruturado em português, pronto para consulta rápida.

## 💡 Por que eu fiz isso

Como praticante e estudioso de hipertrofia, preciso ler bastante 
literatura científica pra calibrar meu próprio treino. Ler abstract 
em inglês, artigo por artigo, é lento. Esse bot resolve isso: cola o 
link, recebe metodologia + achado principal + aplicação prática, 
em português, em segundos.

## ⚙️ Como funciona

1. **Input**: link de um artigo do PubMed
2. **Scraping**: busca o HTML da página (HTTP Request)
3. **Extração**: pega só o título e o abstract, ignorando o resto do HTML (node HTML + CSS Selector)
4. **IA**: envia para a Groq (Llama 3.3 70B) via API, pedindo resumo estruturado
5. **Output**: texto limpo, organizado em 3 seções

## 🛠️ Stack

- **N8N** (automação/orquestração, self-hosted)
- **Groq API** (LLM gratuito, Llama 3.3 70B)
- HTML parsing via CSS Selector

## ⚠️ Limitação atual

Funciona especificamente com a estrutura de página do PubMed 
(seletor `#eng-abstract`). Não generaliza para qualquer site — 
é um trade-off consciente entre robustez e simplicidade para o 
caso de uso real.

## 🚀 Como rodar

1. Instale o N8N: `npx n8n`
2. Importe o arquivo `workflow.json` deste repositório
3. Configure sua própria API Key da Groq (gratuita em [console.groq.com](https://console.groq.com))
4. Cole um link do PubMed no node inicial e execute

---

Este é o primeiro de uma série de projetos práticos de automação + IA.
