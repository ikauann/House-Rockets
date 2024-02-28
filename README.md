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

