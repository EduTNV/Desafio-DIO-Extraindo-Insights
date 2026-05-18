# 🏦 Extraindo Insights do Feedback de Clientes Bancários

Desafio Criativo do **Bootcamp Bradesco GenAI, Dados e Cybersec** — [DIO](https://web.dio.me)

---

## 📋 Sobre o desafio

O objetivo foi construir um prompt estruturado capaz de orientar uma IA a extrair insights reais de feedbacks de clientes bancários, seguindo três etapas progressivas:

1. Definir a intenção da análise
2. Adicionar contexto, dados disponíveis e restrições
3. Unir tudo em um prompt final coeso e acionável

---

## 🗂️ Arquivo de entrega

| Arquivo | Descrição |
|---|---|
| [`desafio-feedback-bancario.md`](./desafio-feedback-bancario.md) | Prompt completo com os 3 passos resolvidos |

---

## 🎯 Abordagem

A análise vai além do genérico: o prompt distingue **falhas operacionais** (lentidão, timeout, erro de autenticação) de **falhas de confiança e segurança percebida** (transações suspeitas, falta de feedback, sensação de vulnerabilidade) — dimensão crítica em um contexto de engenharia social e phishing direcionado a usuários de apps bancários.

Destaques técnicos do prompt construído:

- Campos de dados que refletem pipelines reais (`categoria_auto` via ML, `id_sessao_anonimizado`)
- Separação de ações por responsável: **produto digital** vs. **segurança do cliente**
- Restrições explícitas de **LGPD** e linguagem de "percepção" vs. "fraude confirmada"
- Critério de qualidade objetivo: qualquer analista sem contexto técnico consegue agir só com o output

---

## 🛠️ Tecnologias e conceitos aplicados

- Prompt Engineering
- Análise de sentimento e classificação temática
- LGPD e privacidade de dados
- Segurança percebida em canais digitais bancários
- GenAI aplicada a dados não estruturados

---

## 👤 Autor

**Eduardo Travassos**  
Estudante de Ciência da Computação — Universidade Anhembi Morumbi  
[LinkedIn](https://www.linkedin.com/in/eduardo-travassos) • [GitHub](https://github.com/EduTNV)
