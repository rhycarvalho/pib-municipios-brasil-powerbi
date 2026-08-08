# pib-municipios-brasil-powerbi
Análise da concentração de PIB nos 100 maiores municípios do Brasil - dados do IBGE, tratados e modelados em Power BI.

# PIB dos 100 Maiores Municípios do Brasil

Análise da concentração de PIB no Brasil, usando dados oficiais do IBGE (ano-base 2020) sobre os 100 municípios com maior Produto Interno Bruto do país.

## Por que esse projeto

Depois de fazer um projeto com dataset internacional (vendas), quis pegar dado público brasileiro de verdade — sem curadoria pronta, do jeito que sai direto do site do governo. O objetivo era treinar limpeza de dados pesada dentro do próprio Power Query, sem recorrer a nada externo.

## A pergunta principal

O Brasil tem cerca de 5.570 municípios. Quanto da riqueza do país está concentrada só nos 100 maiores?

## O dado bruto era bagunçado, e isso fez parte do trabalho

O CSV original do IBGE veio com vários problemas clássicos de dado público:
- Cabeçalhos de coluna quebrados em várias linhas dentro da mesma célula
- Município e UF juntos no mesmo campo, tipo "São Paulo (SP)"
- Posição no ranking como texto, com "º" no meio ("1º", "2º")
- Valores de PIB com espaço como separador de milhar
- Nenhuma coluna de região — só a sigla do estado

Tratei tudo isso dentro do Power Query: separei município e UF com Dividir Coluna, limpi os caracteres com Substituir Valores, converti os tipos, e criei a coluna de Região com uma Coluna Condicional mapeando as 27 UFs manualmente. Foi o processo mais próximo de "trabalho real de analista" que fiz até agora.

## O que os dados mostram

- Os 100 maiores municípios concentram **52,92%** de todo o PIB do Brasil — ou seja, menos de 2% dos municípios do país geram mais da metade da riqueza nacional.
- **São Paulo** sozinha responde por quase 10% do PIB nacional, quase o dobro do 2º colocado (Rio de Janeiro).
- **Sudeste** domina a lista: 55 dos 100 municípios estão lá, somando mais de R$ 2,5 trilhões.
- O estado de **São Paulo** tem 35 municípios no Top 100 — mais que o dobro do segundo colocado (RJ, com 10).
- **Norte** é a região menos representada, com só 6 municípios entre os 100 maiores — reflexo direto da diferença de desenvolvimento econômico regional do país.

## O dashboard

Página única com: cartões de KPI (PIB total, participação acumulada, número de municípios), PIB por região, mapa geográfico do Brasil com bolhas proporcionais ao PIB, e ranking dos maiores municípios. Botão de reset de filtros pra facilitar a navegação.

![Visão geral do dashboard] está anexo

## Ferramentas

- Power BI Desktop (Power Query, Coluna Condicional, DAX, visual de mapa)
- Fonte: [IBGE - Produto Interno Bruto dos Municípios](https://www.ibge.gov.br/)

## Como abrir

1. Baixe o `.pbix` na pasta `powerbi/`
2. Abra no Power BI Desktop
