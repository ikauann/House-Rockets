# House Rocket - Análise de Compra e Venda de Imóveis

## Descrição

House Rocket é uma empresa que trabalha com a compra e venda de imóveis. O Cientista de Dados da empresa tem como objetivo ajudar a encontrar as melhores oportunidades de negócio, ou seja, maximizar a receita. A estratégia principal é a compra de casas em ótimas condições por preços baixos e a subsequente venda desses imóveis por um preço superior. Os atributos das casas influenciam diretamente na atratividade e no preço dos imóveis. As principais questões a serem respondidas são:

1. Quais casas o CEO da House Rocket deveria comprar e por qual preço de compra?
2. Uma vez que a casa está em posse da empresa, qual é o melhor momento para vendê-las e qual seria o preço de venda?

## Atributos

Os dados para este projeto podem ser encontrados em: [Kaggle - House Sales Prediction](https://www.kaggle.com/harlfoxem/housesalesprediction/discussion/207885). Abaixo segue a definição para cada um dos 21 atributos:

| Atributo        | Significado                                                  |
|-----------------|--------------------------------------------------------------|
| id              | Numeração única de identificação de cada imóvel              |
| date            | Data da venda da casa                                        |
| price           | Preço que a casa está sendo vendida pelo proprietário        |
| bedrooms        | Número de quartos                                            |
| bathrooms       | Número de banheiros (0.5 = banheiro em um quarto, sem chuveiro) |
| sqft_living     | Medida (em pés quadrados) do espaço interior dos apartamentos |
| sqft_lot        | Medida (em pés quadrados) do espaço terrestre                |
| floors          | Número de andares do imóvel                                  |
| waterfront      | Variável que indica a presença ou não de vista para água (0 = não, 1 = sim) |
| view            | Índice de 0 a 4 que indica a qualidade da vista da propriedade |
| condition       | Índice de 1 a 5 que indica a condição da casa               |
| grade           | Índice de 1 a 13 que indica a construção e o design do edifício |
| sqft_basement   | Metragem quadrada do espaço habitacional interior acima do nível do solo |
| yr_built        | Ano de construção de cada imóvel                             |
| yr_renovated    | Ano de reforma de cada imóvel                                |
| zipcode         | CEP da casa                                                  |
| lat             | Latitude                                                     |
| long            | Longitude                                                    |
| sqft_living15   | Medida (em pés quadrados) do espaço interno de habitação para os 15 vizinhos mais próximos |
| sqft_lot15      | Medida (em pés quadrados) dos lotes de terra dos 15 vizinhos mais próximos |

## Premissas do Negócio

As seguintes premissas foram adotadas para este projeto:

- Os valores iguais a zero em yr_renovated representam casas que nunca foram reformadas.
- O valor igual a 33 na coluna bathroom foi considerado um erro e foi eliminado das análises.
- A coluna price representa o preço que a casa foi ou será comprada pela empresa House Rocket.
- Valores duplicados em ID foram removidos, considerando apenas a compra mais recente.
- A localização e a condição do imóvel foram características decisivas na compra ou não do imóvel.
- A estação do ano foi a característica decisiva para a época da venda do imóvel.

## Estratégia de Solução

As etapas para solucionar o problema de negócio foram as seguintes:

1. Coleta de dados via Kaggle.
2. Entendimento de negócio.
3. Tratamento de dados:
   - Transformação de variáveis.
   - Limpeza.
   - Entendimento.
4. Exploração de dados.

## Insights Principais

### Insights mais relevantes para o projeto:

1. **Imóveis renovados recentemente são 35% mais caros**
   - **Falso:** Imóveis antigos e atuais possuem uma faixa de preço equivalente.

2. **Imóveis em más condições, mas com uma boa vista são 10% mais caros**
   - **Falso:** Imóveis em más condições e com vista ruim são mais caros.

3. **Crescimento do preço mês após mês em 2014 é de 10%**
   - **Falso:** O preço dos imóveis são mais caros entre o mês 3 e 6.

# Tradução para o Negócio

### O que as análises das hipóteses dizem sobre o negócio:

| Hipótese | Resultado | Tradução para o Negócio |
|----------|-----------|-------------------------|
| H1 - Imóveis com vista para a água são em média 30% mais caros | Verdadeira | Investir em imóveis com vista para água |
| H2 - Imóveis com data de construção menor que 1955 são em média 50% mais baratos | Falsa | Investir em imóveis independente da data de construção |
| H3 - Imóveis sem porão com maior área total são 40% mais caros | Verdadeira | Investir em imóveis sem porão |
| H4 - Imóveis que nunca foram reformados são em média 20% mais baratos | Verdadeira | Investir em imóveis não reformados e reformá-los para venda |
| H5 - Imóveis em más condições, mas com boa vista são 10% mais caros | Falsa | Não investir em imóveis em más condições |
| H6 - Imóveis antigos e não renovados são 40% mais baratos | Verdadeira | Investir em imóveis antigos e não renovados e reformá-los para venda |
| H7 - Imóveis com mais banheiros são em média 5% mais caros | Falsa | Investir em imóveis de 3-5 banheiros |
| H8 - Imóveis renovados recentemente são 35% mais caros | Falsa | Investir em imóveis independente da reforma |
| H9 - O crescimento do preço dos imóveis mês após mês no ano de 2014 é de 10% | Falsa | Investir em imóveis nos meses de menor custo |
| H10 - Imóveis com 3 banheiros têm um crescimento mês após mês de 15% | Falsa | Investir em imóveis nos meses de menor custo |

**O valor total de lucro (lucro = preço de compra - preço de venda) dos imóveis é de: $22.623.548,20**

# Conclusão

O objetivo final deste projeto era responder a duas questões principais:

1. Quais casas o CEO da House Rocket deveria comprar e por qual preço de compra?
2. Uma vez a casa em posse da empresa, qual o melhor momento para vendê-las e qual seria o preço da venda?

Os objetivos foram alcançados. Os imóveis foram agrupados por região (zipcode). Considerando o preço do imóvel e a condição (1 - 5), foi calculada a mediana do preço. Imóveis abaixo do preço da mediana e com melhores condições foram sugeridos para compra (total de 151 imóveis). Os imóveis aptos para compra foram agrupados pela localidade e a estação do ano. A mediana foi calculada e imóveis com preço abaixo da mediana tiveram um acréscimo de 10% em seu valor, enquanto imóveis com preço acima da mediana tiveram um acréscimo de 30% acima do seu valor. O melhor momento para a venda dos imóveis é na primavera, uma vez que o preço é maior nessa época.

Como próximo passo, seria interessante a análise de quais apartamentos deveriam sofrer reformas, uma vez que imóveis antigos e não reformados são mais baratos, enquanto imóveis renovados recentemente são mais caros. Também é de interesse prever a valorização do imóvel, pois pode permitir reter a venda da habitação até esta estar mais valorizada no mercado.


