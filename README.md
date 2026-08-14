# PIB dos 100 Maiores Municípios do Brasil - Power BI

Análise da concentração de riqueza no Brasil utilizando dados oficiais do IBGE (ano-base 2020) sobre os 100 municípios com maior Produto Interno Bruto (PIB) do país. Tudo tratado e modelado no Power BI.

## Por que fiz esse projeto?

 A ideia era pegar o arquivo bruto, do jeito que sai do portal do governo, para treinar limpeza pesada de dados direto no Power Query, sem usar Excel ou Python no meio do caminho.

## A pergunta principal

O Brasil tem 5.570 municípios. Desse total, qual é a fatia de toda a riqueza nacional que fica concentrada apenas nos 100 maiores?

## Os dados vieram bem bagunçados (e essa era a intenção)

O CSV original do IBGE veio com aqueles problemas clássicos de dados públicos:
- Cabeçalhos quebrados em várias linhas dentro da mesma célula.
- Município e UF misturados na mesma coluna (ex: "São Paulo (SP)").
- Posição no ranking formatada como texto, com o "º" no meio ("1º", "2º").
- Valores do PIB com espaço como separador de milhar.
- Faltava uma coluna indicando a região do país (tinha apenas a sigla do estado).

Tratei tudo isso 100% no Power Query: separei município e UF com o *Dividir Coluna*, limpei a sujeira dos textos com *Substituir Valores*, arrumei os tipos de dados e criei a coluna de Região usando uma *Coluna Condicional* para mapear as 27 UFs na mão. Foi a experiência mais próxima do "dia a dia real" de um analista que tive até agora.

## Principais insights

- Os 100 maiores municípios concentram **52,92%** de todo o PIB do Brasil. Ou seja, menos de 2% das cidades geram mais da metade da riqueza do país.
- **São Paulo (SP)** sozinha responde por quase 10% do PIB nacional, praticamente o dobro do 2º colocado (Rio de Janeiro).
- O **Sudeste** domina o ranking: 55 dos 100 municípios estão lá, somando mais de R$ 2,5 trilhões.
- Só o estado de **São Paulo** tem 35 cidades no Top 100 — muito à frente do segundo colocado (RJ, com 10).
- A região **Norte** é a que tem a menor participação, com apenas 6 municípios entre os maiores, um reflexo direto da desigualdade econômica regional.

## O Dashboard

Fiz um painel de página única (one-page) contendo: 
- Cartões de KPI (PIB total, participação acumulada e número de municípios).
- Gráfico do PIB por Região.
- Mapa geográfico do Brasil com bolhas proporcionais ao tamanho do PIB.
- Tabela com o ranking dos maiores municípios. 
- Um botão de reset de filtros para facilitar a navegação de quem está usando.

![Visão geral do dashboard]  -> dashboard pib .png

## Ferramentas utilizadas

- **Power BI Desktop** (Power Query, Colunas Condicionais, DAX e visuais de mapa).
- **Fonte dos Dados:** [IBGE - Produto Interno Bruto dos Municípios](https://www.ibge.gov.br/)
