# 🚀 Desafio Criativo: Planejando Automações com N8N Usando Apenas Bons Prompts

![N8N](https://img.shields.io/badge/n8n-Workflow_Automation-FF6D5A?style=for-the-badge&logo=n8n&logoColor=white)
![Google Sheets](https://img.shields.io/badge/Google_Sheets-34A853?style=for-the-badge&logo=google-sheets&logoColor=white)
![Gmail](https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white)
![Prompt Engineering](https://img.shields.io/badge/IA-Prompt_Engineering-8A2BE2?style=for-the-badge)

Repositório criado para a entrega do **Desafio Criativo** do **Bootcamp Santander 2026 - Automação com N8N** na [DIO](https://www.dio.me/).

---

## 🎯 Objetivo do Desafio

Planejar e estruturar uma automação completa no **n8n** utilizando técnicas de **Engenharia de Prompts** (definição de Persona, Contexto, Ferramentas, Fluxo Lógico e Regras de Negócio) para automatizar o fechamento financeiro semanal de despesas usando **Google Sheets** e **Gmail**.

---

## 🧱 Passo 1: Definição da Automação Desejada

> **Quero criar uma automação no N8N para:** analisar as despesas registradas ao longo da semana e gerar um fechamento financeiro automático.
>
> **Público ou responsável:** Equipe financeira (ou uso pessoal para controle de gastos).
>
> **Resultado esperado:** Somar os gastos da semana, destacar despesas altas e enviar um resumo organizado por e-mail toda sexta-feira.

---

## 🧱 Passo 2: Contexto, Ferramentas e Regras

* **Ferramentas envolvidas:** Google Sheets e Gmail (além dos nós nativos de Agendamento e Filtro do N8N).
* **Fluxo desejado:**
  1. Disparar a automação automaticamente toda sexta-feira às 17h.
  2. Ler os registros de despesas da semana na planilha do Google Sheets.
  3. Filtrar os dados válidos, calcular o total gasto na semana e identificar despesas acima de R$ 500.
  4. Enviar um e-mail pelo Gmail com o resumo semanal formatado.
* **Regras importantes:**
  * Ignorar linhas com valor igual a zero ou sem valor preenchido.
  * Destacar em vermelho no corpo do e-mail todas as despesas que ultrapassarem R$ 500,00.

---

## 🧠 Passo 3: Prompt Final Estruturado

```text
Atue como um especialista em N8N.

Crie uma automação para analisar as despesas registradas ao longo da semana e gerar um fechamento financeiro automático.

Público:
Equipe financeira (ou uso pessoal para controle de gastos).

Ferramentas envolvidas:
Google Sheets e Gmail (além dos nós nativos de Agendamento e Filtro do N8N).

Fluxo:
1. Disparar a automação automaticamente toda sexta-feira às 17h.
2. Ler os registros de despesas da semana na planilha do Google Sheets.
3. Filtrar os dados válidos, calcular o total gasto na semana e identificar despesas acima de R$ 500.
4. Enviar um e-mail pelo Gmail com o resumo semanal formatado.

Regras:
- Ignorar linhas com valor igual a zero ou sem valor preenchido.
- Destacar em vermelho no corpo do e-mail todas as despesas que ultrapassarem R$ 500,00.

Explique quais nós do N8N devem ser utilizados e a lógica de funcionamento do workflow.
```

---

## ⚙️ Arquitetura do Workflow no N8N (Gerada pelo Prompt)

| Ordem | Nó do N8N | Função no Fluxo |
| :---: | :--- | :--- |
| **1** | `Schedule Trigger` | Dispara automaticamente toda sexta-feira às 17:00 (`America/Sao_Paulo`). |
| **2** | `Google Sheets (Get Rows)` | Lê os registros de despesas lançados na planilha da semana. |
| **3** | `Filter` | Valida e descarta linhas com valor vazio ou igual a zero (`valor > 0`). |
| **4** | `Code / Summarize` | Soma o total semanal e aplica destaque em vermelho (`#ff0000`) nos gastos `> R$ 500`. |
| **5** | `Gmail (Send Message)` | Envia o relatório HTML consolidado para o responsável financeiro. |

---

## 👨‍💻 Autor

Desenvolvido por **João Pedro Santos** ([@Joaopedros27](https://github.com/Joaopedros27)) — Bootcamp **Santander 2026 - Automação com N8N** (DIO).
