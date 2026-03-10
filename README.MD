# Telecom X - Previsão de Evasão de Clientes (Churn) - Parte 2

## 📌 Propósito do Projeto

Este projeto tem como objetivo **prever a evasão de clientes (churn)** em uma empresa de telecomunicações utilizando técnicas de **Machine Learning**.

A análise busca identificar **quais fatores influenciam o cancelamento de clientes**, permitindo que a empresa desenvolva **estratégias de retenção mais eficazes**.

Para isso, foram analisadas variáveis relacionadas ao perfil do cliente, tipo de contrato, serviços utilizados e valores de cobrança.


# 📊 Preparação dos Dados

Antes da modelagem, foi realizado um processo de preparação dos dados para garantir melhor desempenho dos modelos.

## Classificação das Variáveis

As variáveis foram classificadas em:

**Variáveis Numéricas**

- tempo_contrato_meses
- cobranca_mensal
- cobranca_total
- cobranca_diaria

**Variáveis Categóricas**

- genero
- tipo_contrato
- tipo_internet
- metodo_pagamento
- possui_parceiro
- possui_dependentes
- suporte_tecnico
- seguranca_online
- streaming_tv
- streaming_filmes
- entre outras.

---

# 🔄 Etapas de Pré-Processamento

## Codificação de Variáveis

Variáveis categóricas foram transformadas em variáveis numéricas utilizando **One-Hot Encoding**, permitindo que os modelos de Machine Learning pudessem utilizá-las corretamente.

## Normalização dos Dados

Para modelos sensíveis à escala dos dados (como **Regressão Logística**), foi utilizada **padronização com StandardScaler**.

A normalização garante que todas as variáveis estejam na mesma escala, evitando que variáveis com valores maiores tenham influência desproporcional no modelo.

## Separação dos Dados

Os dados foram divididos em:

- **70% para treino**
- **30% para teste**

Utilizando a função `train_test_split` da biblioteca **Scikit-learn**, com `stratify` aplicado para manter a proporção da variável alvo.

---

# 🤖 Modelagem

Foram treinados dois modelos de Machine Learning para prever a evasão de clientes.

## Regressão Logística

A Regressão Logística é um modelo estatístico amplamente utilizado para **problemas de classificação binária**, como churn (evasão ou permanência).

Ela foi escolhida por ser um modelo **interpretável**, permitindo analisar o impacto das variáveis por meio de seus coeficientes.

## Random Forest

O Random Forest é um modelo baseado em **árvores de decisão**, capaz de capturar relações mais complexas entre variáveis.

Esse modelo também fornece métricas de **importância das variáveis**, permitindo identificar quais fatores mais influenciam a evasão de clientes.

---

# 📈 Avaliação dos Modelos

Os modelos foram avaliados utilizando as seguintes métricas:

- **Acurácia**
- **Precisão**
- **Recall**
- **F1-Score**
- **Matriz de Confusão**

A Regressão Logística apresentou desempenho ligeiramente superior ao Random Forest, demonstrando maior capacidade de identificar clientes com maior probabilidade de churn.

---

# 🔎 Análise Exploratória de Dados (EDA)

Durante a análise exploratória, foram utilizados diversos gráficos para entender a relação entre variáveis e evasão.

Alguns exemplos incluem:

### Tempo de contrato × Evasão
Clientes com menor tempo de contrato apresentaram maior tendência a cancelar o serviço.

### Total gasto × Evasão
Foi observado que clientes com maiores valores de cobrança podem apresentar maior risco de churn, possivelmente devido à percepção de custo-benefício.

### Tipo de contrato × Evasão
Clientes com contratos **Month-to-month** demonstraram maior probabilidade de evasão quando comparados a contratos anuais.

Esses insights ajudam a compreender os fatores que influenciam o comportamento dos clientes.

---

# 📊 Importância das Variáveis

A análise de importância das variáveis revelou fatores relevantes para a previsão de churn, como:

- tipo_contrato_Month-to-month
- cobranca_total
- cobranca_mensal
- tempo_contrato_meses
- tipo_internet_Fiber optic
- metodo_pagamento_Electronic check

Essas variáveis indicam que fatores financeiros e o tipo de contrato possuem forte influência no comportamento de cancelamento.

---

# 💡 Estratégias de Retenção

Com base nos resultados obtidos, algumas estratégias podem ser propostas:

- Incentivar **contratos de longo prazo** com benefícios ou descontos.
- Monitorar clientes com **contratos mensais**, que apresentam maior risco de evasão.
- Melhorar a **percepção de valor do serviço**, principalmente para clientes com cobranças mais altas.
- Oferecer **serviços adicionais**, como suporte técnico e segurança online.

---

# ▶️ Como Executar o Projeto

## 1️⃣ Instalar as bibliotecas necessárias

```bash
pip install pandas numpy matplotlib seaborn scikit-learn