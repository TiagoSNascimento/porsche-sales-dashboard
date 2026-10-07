# Porsche Sales Dashboard

Dashboard interativa criada a partir do desafio da DIO **Criando uma Dashboard de Vendas da Porsche**.

## 🎯 Objetivo

Transformar a planilha de vendas em uma experiência analítica simples, interativa e publicável no GitHub Pages, usando somente as colunas sanitizadas da base.

## 📊 Perguntas de negócio

### 1. Quais modelos geram mais receita?
**Por quê?** Ajuda a identificar quais veículos têm maior contribuição financeira e quais modelos merecem atenção comercial.

**Visual:** ranking dos 10 modelos com maior receita.

### 2. Quais estados concentram a receita?
**Por quê?** Permite enxergar os mercados geográficos mais relevantes e apoiar decisões de priorização comercial.

**Visual:** ranking dos 10 estados com maior receita.

### 3. Quais meios de pagamento movimentam mais valor?
**Por quê?** Mostra como a receita está distribuída entre as diferentes formas de pagamento e ajuda a entender o comportamento financeiro das vendas.

**Visual:** gráfico de rosca por método de pagamento.

## 🔎 Filtros

A dashboard permite cruzar:
- Modelo;
- Estado;
- Cidade;
- Ano do veículo;
- Método de pagamento.

Os indicadores e os três gráficos são recalculados conforme os filtros.

## 🧹 Tratamento da base

A planilha original possui campos crus e campos sanitizados. Para a dashboard foram utilizadas **somente as colunas sanitizadas**:

- `SaleDateSanitized`
- `PorscheModelSanitized`
- `ModelYearSanitized`
- `SalesPriceSanitized`
- `VehicleMileageSanitized`
- `PayMethodSanitized`
- `CitySanitized`
- `StateSanitized`
- `DeliveryStatusSanitized`

O preço já sanitizado foi tratado como número e o ano do veículo como número inteiro.

A base contém 100 vendas. A coluna de data sanitizada possui registros `INVALID`; esses registros foram mantidos na base, sem tentar inventar uma data. Como as três perguntas escolhidas não dependem da data de venda, nenhuma informação foi descartada por esse motivo.

Também foram excluídos da dashboard os campos pessoais/identificadores que não eram necessários para responder às perguntas de negócio.

## 🤖 Prompt utilizado

> Tenho uma base sanitizada com 100 vendas da Porsche, contendo modelo, ano do veículo, preço, quilometragem, método de pagamento, cidade, estado e status de entrega.
>
> Quero criar uma dashboard em HTML, responsiva e interativa, para análise executiva de vendas.
>
> As perguntas de negócio são:
> 1. Quais modelos geram mais receita?
> 2. Quais estados concentram a receita?
> 3. Quais meios de pagamento movimentam mais valor?
>
> A dashboard deve ter indicadores de total de vendas, receita, ticket médio e quilometragem média; filtros por modelo, estado, cidade, ano e método de pagamento; e gráficos que sejam atualizados pelos filtros.
>
> Use somente os dados sanitizados. Não invente valores para registros inválidos. O resultado deve ser um único arquivo `index.html`, com visual premium inspirado na identidade da Porsche, boa legibilidade, responsividade e sem depender de Excel.
>
> Priorize clareza analítica em vez de excesso de gráficos.

### Evolução do prompt

A primeira preocupação foi definir as **perguntas de negócio antes dos gráficos**. Depois, foram acrescentados:
- filtros com atualização cruzada;
- KPIs executivos;
- tratamento explícito de `INVALID`;
- uso exclusivo das colunas sanitizadas;
- layout responsivo;
- visual inspirado na Porsche;
- manutenção dos 100 registros, evitando perda desnecessária de dados.

## 🛠️ Ferramenta

O projeto foi construído com **ChatGPT**, usando a planilha como fonte de dados e refinando a solução em linguagem natural.

## 📁 Estrutura

```text
porsche-sales-dashboard/
├── index.html
└── README.md
```

## 🚀 Publicação no GitHub Pages

1. Crie um repositório público com nome, por exemplo:
   `porsche-sales-dashboard`
2. Coloque `index.html` e `README.md` na raiz.
3. Faça o commit e o push.
4. No GitHub, abra **Settings → Pages**.
5. Em **Build and deployment**, selecione:
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/ (root)`
6. Salve e aguarde a publicação.
7. O GitHub fornecerá o endereço da dashboard.

### Endereço da dashboard

Após publicar, substitua este trecho pelo link real:

`https://SEU-USUARIO.github.io/porsche-sales-dashboard/`

### Repositório

Substitua pelo endereço real do seu repositório:

`https://github.com/SEU-USUARIO/porsche-sales-dashboard`

## 🖼️ Evidências recomendadas para a entrega

Inclua no README:
- print da dashboard sem filtros;
- print com pelo menos um filtro aplicado;
- link do repositório;
- link da dashboard publicada.

## 💡 Próximas evoluções

- Adicionar análise temporal somente para datas válidas;
- trocar o ranking de estados por mapa;
- comparar receita e quantidade de vendas simultaneamente;
- adicionar análise de status de entrega;
- atualizar a dashboard com uma nova base;
- criar uma versão com componentes semelhantes ao Power BI.

---

**Projeto desenvolvido como exercício de análise de dados, visualização e uso de IA para construção de dashboards.**
