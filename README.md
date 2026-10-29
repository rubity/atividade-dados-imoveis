# Atividade: preparação de dados de aluguel

Nesta atividade você vai trabalhar com os dados de uma imobiliária fictícia da cidade de Vila Nova. A imobiliária juntou anúncios de aluguel de várias fontes e quer, no futuro, treinar um modelo para prever o preço do aluguel. Antes disso, os dados precisam ser avaliados e preparados.

Você não vai treinar nenhum modelo aqui. O foco é entender os dados, encontrar o que está errado e decidir o que fazer com cada problema.

## Como começar

1. Abra o Google Colab em colab.research.google.com e crie um notebook novo.
2. Dê ao notebook o nome `atividade_dados_seunome`.
3. Na primeira célula, cole o código abaixo para carregar os dados direto deste repositório.

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

url = "https://raw.githubusercontent.com/rubity/atividade-dados-imoveis/main/dados/imoveis.csv"
df = pd.read_csv(url)

df.head()
```

Se preferir baixar o repositório inteiro, também funciona:

```python
!git clone https://github.com/rubity/atividade-dados-imoveis.git
df = pd.read_csv("atividade-dados-imoveis/dados/imoveis.csv")
```

Se aparecer algum erro de leitura, confira se a url está correta e se o arquivo está em `dados/imoveis.csv`.

## Sobre os dados

O arquivo tem uma linha por anúncio. Os dados foram montados de propósito com vários problemas, como acontece com dados reais.

| Coluna | O que é |
|---|---|
| id_anuncio | Número do anúncio |
| bairro | Bairro do imóvel |
| tipo | Apartamento, casa ou kitnet |
| area_m2 | Área em metros quadrados |
| area_pes2 | Área em pés quadrados |
| quartos | Número de quartos |
| banheiros | Número de banheiros |
| vagas_garagem | Vagas de garagem |
| andar | Andar do imóvel |
| idade_imovel_anos | Idade do imóvel em anos |
| distancia_metro_km | Distância até a estação de metrô mais próxima |
| condicao | Estado do imóvel: novo, bom ou reformar |
| pontuacao_seguranca | Nota de 1 a 10 dada em uma pesquisa com moradores |
| possui_piscina | Se tem piscina |
| cidade | Cidade do anúncio |
| preco_aluguel | Valor do aluguel mensal em reais |

A coluna que a imobiliária quer prever no futuro é `preco_aluguel`.

## O que fazer

Faça tudo no mesmo notebook, na ordem abaixo. Escreva um texto curto em uma célula de texto depois de cada etapa explicando o que encontrou e o que decidiu.

**1. Conhecer os dados.** Veja o tamanho da tabela, os tipos de cada coluna, as estatísticas básicas e a porcentagem de valores preenchidos em cada coluna. Anote o que chamou sua atenção.

**2. Correlações.** Monte uma matriz de correlação e um gráfico para visualizar. Quais atributos parecem mais ligados ao preço? Existe algum par de colunas que diz quase a mesma coisa?

**3. Limpeza.** Trate os valores ausentes, as linhas repetidas e os textos escritos de formas diferentes. Cada coluna com valores ausentes pode pedir uma solução diferente, então pense em cada uma separadamente.

**4. Valores extremos.** Procure valores muito altos, muito baixos ou impossíveis. Decida o que é erro e o que é um dado real que só é raro.

**5. Escolha de atributos.** Decida quais colunas vão ficar e quais vão sair, e explique por quê.

**6. Codificação.** Transforme as colunas de texto que ficaram em números, escolhendo a técnica mais adequada para cada uma.

**7. Resumo das decisões.** No final do notebook, faça uma tabela com três colunas: problema encontrado, o que você fez e por que fez.

## Regras e dicas

Não existe uma única resposta certa. O que vale é a decisão ser coerente e bem justificada.

Escreva as justificativas com as suas palavras. Código sem explicação não conta como resposta.

Algumas dicas: nem todo valor ausente significa a mesma coisa, nem todo valor extremo é um erro, e vale olhar para o dado antes e depois de cada mudança para ter certeza de que a correção funcionou. Pesquisar na documentação do pandas é permitido e esperado.

## Entrega

Entregue o link do seu notebook no Colab, com o compartilhamento aberto para quem tem o link. Antes de enviar, use a opção Ambiente de execução, Executar tudo, para garantir que o notebook roda do início ao fim sem erros. Prazo e forma de envio serão combinados em aula.

## Como será avaliado

| Critério | Peso |
|---|---|
| Exploração dos dados e correlações | 20% |
| Limpeza (ausentes, duplicados, textos) | 25% |
| Tratamento de valores extremos | 15% |
| Escolha de atributos e codificação | 20% |
| Justificativas, organização e notebook rodando | 20% |
