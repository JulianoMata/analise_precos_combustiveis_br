## 📈 Resultados Principais

Nesta seção, apresentamos as principais visualizações geradas pelo projeto, ilustrando a análise histórica e a previsão de preços, seguidas da análise textual detalhada dos resultados.

### Evolução do Preço Médio de Combustíveis por Região

Este gráfico multifacetado mostra a variação do preço médio de venda para os quatro combustíveis analisados em todas as regiões do Brasil ao longo do tempo. Ele destaca eventos significativos, como as quedas abruptas de preço em 2022, e as disparidades regionais.

![Evolução do Preço Médio de Combustíveis por Região](imagens/evolucao_precos_por_regiao.png)

### Previsão de Preço para Gasolina na Região Sudeste

Esta visualização apresenta a previsão do modelo Prophet para o preço da gasolina na Região Sudeste, incluindo os dados históricos (pontos pretos), a linha de previsão (azul escura) e o intervalo de confiança (área azul clara), que evidencia a incerteza da projeção.

![Previsão de Preço - GASOLINA Região Sudeste](imagens/forecast_gasolina_sudeste.png)

### Componentes da Previsão (Tendência e Sazonalidade)

Este gráfico detalha os componentes subjacentes da previsão do Prophet. O painel superior exibe a tendência de longo prazo (`trend`), enquanto o inferior mostra o padrão de sazonalidade anual (`yearly`), revelando como esses elementos contribuem para a projeção final de preços.

![Componentes da Previsão - GASOLINA Região Sudeste](imagens/forecast_components_gasolina_sudeste.png)

### Análise Detalhada dos Resultados

A execução deste projeto atingiu com sucesso os objetivos de análise descritiva e preditiva propostos:

**1. Análise Histórica**

A visualização facetada (gráfico `evolucao_precos_por_regiao.png`) validou a metodologia de ETL e permitiu confirmar visualmente as seguintes hipóteses:

* **Análise por Produto:** A Gasolina e o Diesel S10 competem consistentemente pelos postos de combustíveis mais caros, enquanto o Etanol e o GNV (onde disponível) se consolidam como as alternativas econômicas.
* **Análise Regional (Preços Altos):** As regiões **Norte** e **Nordeste** apresentam custos estruturalmente mais elevados para combustíveis fósseis (Gasolina/Diesel), refletindo desafios logísticos de distribuição.
* **Análise Regional (Preços Baixos):** As regiões **Sudeste** e **Centro-Oeste** demonstram ser as mais competitivas do país, apresentando os preços médios mais baixos, especialmente para o Etanol, devido à proximidade dos polos produtores.
* **Análise de Eventos:** A mudança na legislação do ICMS em meados de 2022 foi confirmada como o ponto de inflexão mais significativo da série, causando uma queda estrutural (não sazonal) abrupta em todos os produtos, em todas as regiões.

**2. Análise Preditiva**

O modelo Prophet foi treinado com sucesso para a série temporal da Gasolina na Região Sudeste.

* **Previsão (yhat):** O modelo prevê uma leve tendência de alta contínua para os próximos 12 meses, extrapolando a recuperação gradual observada desde o final de 2022.
* **Incerteza (yhat_upper / yhat_lower):** O principal insight do modelo é o alargamento drástico do intervalo de confiança de 80%. Isso demonstra matematicamente que, devido à alta instabilidade histórica (choques políticos e fiscais) e à dependência de fatores externos, previsões de longo prazo para este mercado possuem **elevada incerteza estatística**.
* **Componentes:** A decomposição do modelo isolou com sucesso a Tendência (identificando o "changepoint" de 2022) e uma clara Sazonalidade Anual (picos no 1º semestre e vales no 2º semestre).