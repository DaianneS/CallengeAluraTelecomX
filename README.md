# CallengeAluraTelecomX
# Análise de Churn de Clientes de Telecomunicações | Oracle ONE + Alura

![Status](https://img.shields.io/badge/status-concluído-brightgreen)
![Python](https://img.shields.io/badge/python-3.9%2B-blue)
![Libraries](https://img.shields.io/badge/libraries-pandas%20%7C%20numpy%20%7C%20seaborn-orange)

## 📄 Sobre o Projeto

Este repositório contém a análise completa sobre a evasão de clientes (Churn) de uma empresa fictícia de telecomunicações, a **TelecomX**. O projeto foi desenvolvido como parte do desafio do programa **Oracle Next Education (ONE) em parceria com a Alura Latam**.

O objetivo principal é realizar um processo completo de **ETL (Extração, Transformação e Carga)** e **Análise Exploratória de Dados (EDA)** para identificar os principais fatores que levam os clientes a cancelarem seus serviços, culminando em um relatório com insights e recomendações estratégicas para a empresa.

---

## 🚀 O Desafio

A evasão de clientes, ou Churn, é uma métrica crítica para qualquer negócio baseado em assinaturas. Um alto índice de Churn impacta diretamente a receita e a sustentabilidade da empresa. O desafio proposto foi analisar uma base de dados complexa para:

1.  Identificar os principais perfis de clientes que cancelam o serviço.
2.  Descobrir quais fatores (demográficos, de serviço, de contrato) mais influenciam essa decisão.
3.  Propor ações estratégicas para aumentar a retenção de clientes.

---

## 🛠️ Tecnologias Utilizadas

- **Linguagem:** Python
- **Bibliotecas:**
  - `Pandas` para manipulação e análise de dados.
  - `NumPy` para operações numéricas.
  - `Matplotlib` e `Seaborn` para visualização de dados.
- **Ambiente:** Jupyter Notebook / Google Colab

---

## ⚙️ Passo a Passo Detalhado

O projeto foi estruturado seguindo um fluxo de trabalho padrão de análise de dados, desde a extração até a geração de insights.

### 1. Extração dos Dados
- Os dados brutos foram carregados a partir de um arquivo `TelecomX_Data.json`.
- A estrutura inicial era complexa, com colunas contendo dados aninhados em formato JSON (`customer`, `phone`, `internet`, `account`), o que exigiu um tratamento especial.

### 2. Transformação e Limpeza de Dados
Esta foi a etapa mais crucial do processo de ETL, onde os dados brutos foram preparados para a análise:

- **Normalização:** A função `pd.json_normalize` foi utilizada para "achatar" as colunas com dados aninhados, transformando-as em colunas tabulares e organizadas.
- **Tradução e Localização:** Todos os valores categóricos em inglês (ex: `Yes`, `No`, `Female`, `Month-to-month`) foram traduzidos para o português (`Sim`, `Não`, `Feminino`, `Mês a mês`). As colunas também foram renomeadas para facilitar a interpretação no contexto brasileiro.
- **Tratamento de Dados Faltantes:** Identificou-se que a coluna `Cancelou` (Churn) possuía registros com valores vazios. Essas linhas foram removidas para garantir a integridade da análise, resultando em um dataset final com **7.032 registros**.
- **Conversão de Tipos:** A coluna `Cobranca_Total` (Total Charges), que estava como objeto (texto), foi convertida para um tipo numérico para permitir cálculos estatísticos.
- **Exportação:** O dataset limpo e transformado foi salvo nos formatos `.csv` e `.json` para futuras análises.

### 3. Análise Exploratória de Dados (EDA)
Com os dados devidamente tratados, a fase de análise visual foi iniciada para descobrir padrões:

- **Análise Geral:** A taxa de Churn geral da empresa é de **26,5%**.
- **Visualizações:** Foram criados diversos gráficos para cruzar a variável `Cancelou` com outros atributos dos clientes e serviços.

---

## 📊 Principais Descobertas e Visualizações

A análise revelou fortes correlações entre o Churn e os seguintes fatores:

#### 1. Contrato Mensal vs. Churn
A maior taxa de churn (**42,7%**) está concentrada em clientes com contrato **Mês a Mês**, indicando que a falta de um vínculo de longo prazo é o principal fator de risco.



#### 2. Cobrança Mensal vs. Churn
Clientes que cancelam tendem a ter uma cobrança mensal mediana mais alta (aprox. R$ 80) em comparação com os que permanecem (aprox. R$ 65).


#### 3. Tempo de Permanência (Tenure) vs. Churn
A evasão é significativamente maior nos primeiros meses de serviço. Clientes com mais de um ano de casa se tornam progressivamente mais leais.


---

## 💡 Conclusões e Recomendações

Com base nas descobertas, foi traçado o **perfil do cliente com alto risco de Churn**:
- Possui contrato **Mês a Mês**.
- É um **cliente novo** (poucos meses de casa).
- Paga uma **fatura mensal elevada**.
- Utiliza **cheque eletrônico** como forma de pagamento.
- É **idoso**, não possui cônjuge ou dependentes.

As **recomendações estratégicas** para a TelecomX incluem:
1.  **Incentivar Contratos de Longo Prazo:** Oferecer descontos ou benefícios exclusivos para clientes que migrarem de planos mensais para anuais ou bianuais.
2.  **Programa de Onboarding:** Criar um acompanhamento especial para clientes nos primeiros 6 meses, garantindo uma boa experiência inicial.
3.  **Revisão de Planos:** Para clientes com contas altas, oferecer pacotes de serviços adicionais (ex: Suporte Técnico, Segurança Online) que aumentem o valor percebido e a "fidelidade" do cliente.
4.  **Otimizar Formas de Pagamento:** Incentivar a migração do cheque eletrônico para métodos automáticos, como cartão de crédito ou débito em conta.

---

## 🚀 Como Executar o Projeto

```bash
# Clone este repositório
git clone [https://github.com/seu-usuario/nome-do-repositorio.git](https://github.com/seu-usuario/nome-do-repositorio.git)

# Navegue até o diretório
cd nome-do-repositorio

# Instale as bibliotecas necessárias
pip install pandas numpy matplotlib seaborn

# Certifique-se de que o arquivo `TelecomX_Data.json` esteja no mesmo diretório.

# Abra o notebook `DaianneSTelecomX_BR.ipynb` em um ambiente como Jupyter ou Google Colab e execute as células.
