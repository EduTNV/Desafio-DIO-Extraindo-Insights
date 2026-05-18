# Desafio Criativo — Extraindo Insights do Feedback de Clientes Bancários

> **Bootcamp:** Bradesco GenAI, Dados e Cybersec — DIO  
> **Desafio:** Construção de prompt para análise de feedbacks de clientes bancários com IA

---

## Sobre o desafio

O objetivo foi construir um prompt capaz de orientar uma IA a extrair insights reais de feedbacks de clientes bancários, seguindo três etapas progressivas: definir a intenção, adicionar contexto e restrições, e unir tudo em um prompt final coeso.

A abordagem escolhida vai além do genérico: o foco está em distinguir **falhas operacionais** (lentidão, timeout, erro de autenticação) de **falhas de confiança e segurança percebida** (transações suspeitas, falta de feedback, sensação de vulnerabilidade) — dimensão crítica em um contexto de aumento de engenharia social e phishing direcionado a usuários de apps bancários.

---

## Passo 1 — Definição da intenção

```
Quero que a IA analise comentários de clientes coletados via canais digitais de um banco —
app móvel, internet banking, atendimento via chat e respostas pós-transação no Pix —
após eventos de falha ou lentidão, para identificar padrões de fricção operacional e
falhas de segurança percebidas pelo cliente.

O resultado será usado pelo squad de produto digital e pela equipe de segurança do
cliente para apoiar a priorização do backlog de melhorias com base em evidências reais
de usuários.

A entrega deve conter um resumo executivo (até 5 linhas), uma tabela com tema,
sentimento dominante, evidência extraída e ação recomendada, e um ranking das 3
falhas com maior impacto percebido pelo cliente.

O resultado será considerado bom se qualquer analista sem contexto técnico conseguir
identificar a próxima ação prioritária sem precisar reler os feedbacks originais.
```

---

## Passo 2 — Contexto e restrições

```
Contexto:
Estou trabalhando com feedbacks de clientes bancários coletados entre jan–abr de 2025,
período marcado por aumento de tentativas de engenharia social direcionadas ao app.
O contexto é sensível: alguns comentários mencionam percepções de fraude e transações
não reconhecidas.

Dados disponíveis:
A base contém os seguintes campos:
- data_feedback
- canal (app, internet banking, chat, pós-Pix)
- produto_citado
- texto_livre
- nota_nps (0–10)
- categoria_auto (tag gerada por modelo ML)
- id_sessao_anonimizado

Critérios de análise:
A IA deve classificar os feedbacks por:
- Tema: operacional / segurança percebida / UX / confiança institucional
- Sentimento: positivo / negativo / neutro
- Urgência: alta se NPS ≤ 4 com menção a fraude ou perda financeira
- Canal e produto citado

Cuidados e restrições:
- Use apenas os dados fornecidos.
- Não invente números, causas ou conclusões.
- Não exponha CPF, nome, agência ou valores que identifiquem o cliente.
- Nunca afirme que houve fraude confirmada — use linguagem de "percepção" ou "relato".
- Se algum tema tiver menos de 10 ocorrências, indique como amostra insuficiente.
- Trate os dados como pseudoanonimizados conforme LGPD.
- Use linguagem executiva: direta, sem jargão técnico de TI.
```

---

## Passo 3 — Prompt final unificado

```
Atue como analista sênior de dados e experiência do cliente em um banco digital.

Sua tarefa é analisar feedbacks de clientes sobre app móvel, internet banking, Pix e
atendimento via chat para identificar padrões de fricção operacional e falhas de
segurança percebidas — distinguindo problemas técnicos (lentidão, timeout, erro de
autenticação) de problemas de confiança (transações suspeitas, falta de feedback,
sensação de vulnerabilidade).

Contexto:
Os feedbacks foram coletados entre jan–abr de 2025, período marcado por aumento de
tentativas de engenharia social direcionadas ao app. A análise será usada pelo squad
de produto e pela equipe de segurança do cliente para priorizar o backlog com base em
evidência real, não suposição. O objetivo é transformar comentários dispersos em
insights acionáveis sem expor dados sensíveis.

Dados disponíveis:
Cada registro contém: data_feedback, canal, produto_citado, texto_livre, nota_nps
(0–10), categoria_auto (tag gerada por modelo ML) e id_sessao_anonimizado.
Não há CPF, nome completo, agência ou valores explícitos nos dados — trate como
pseudoanonimizados conforme LGPD.

Instruções de análise:
1. Classifique cada feedback por: tema (operacional / segurança percebida / UX /
   confiança institucional), sentimento (positivo / negativo / neutro), urgência
   (alta = NPS ≤ 4 com menção a fraude ou perda), canal e produto citado.
2. Identifique os padrões mais frequentes, agrupando feedbacks com semântica similar
   mesmo que usem palavras diferentes.
3. Para cada padrão relevante, cite uma evidência curta extraída do texto original
   (máximo 15 palavras, sem dados pessoais).
4. Sugira ações práticas separadas por responsável: produto digital vs. segurança
   do cliente.

Formato da resposta:
— Resumo executivo (até 5 linhas, foco em decisão).
— Tabela com colunas: Tema | Sentimento | Urgência | Evidência (trecho anonimizado) |
  Ação sugerida.
— Lista final com os 3 problemas de maior impacto percebido, em ordem de prioridade.

Restrições:
- Use apenas os dados fornecidos. Não invente frequências, causas ou conclusões.
- Não exponha nomes, valores, agências ou qualquer dado que identifique o cliente.
- Nunca afirme que houve fraude confirmada — use linguagem de "percepção" ou "relato".
- Se algum tema tiver menos de 10 ocorrências na base, indique como amostra insuficiente.
- Use linguagem executiva: direta, sem jargão técnico de TI, adequada para leitura
  em reunião de produto.
```

---

*Desafio resolvido como parte do Bootcamp Bradesco GenAI, Dados e Cybersec — DIO.*
