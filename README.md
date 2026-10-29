# Atividade: limpeza de dados de aluguel

Esses dados são de uma imobiliária fictícia da cidade de Vila Nova. Ela juntou anúncios de aluguel de vários lugares e um dia quer usar isso para prever o preço do aluguel. Só que os dados vieram bagunçados, do jeito que costuma acontecer na vida real.

A ideia é simples: explorar os dados, achar o que está errado, arrumar do jeito que você achar melhor e salvar uma versão final limpa do dataset. Não precisa treinar nenhum modelo.

## Carregando os dados

Crie um notebook novo no [Google Colab](https://colab.research.google.com) e rode isso na primeira célula:

```python
import pandas as pd

url = "https://raw.githubusercontent.com/rubity/atividade-dados-imoveis/main/dados/imoveis.csv"
df = pd.read_csv(url)
df.head()
```

Depois disso, use as bibliotecas que quiser.

## As colunas

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

O que a imobiliária quer prever no futuro é o `preco_aluguel`, então vale ter isso em mente na hora de decidir o que manter.

## O que fazer

1. **Explore os dados.** Tamanho da tabela, tipos das colunas, estatísticas, gráficos, o que você achar útil para entender o que tem ali.
2. **Trate o que estiver errado.** Você decide o que é problema e como resolver. Não existe uma única resposta certa, só deixe anotado no notebook o que você fez e por quê.
3. **Salve o dataset limpo.** No final, salve a sua versão tratada em um CSV:

```python
df.to_csv("imoveis_limpo.csv", index=False)

from google.colab import files
files.download("imoveis_limpo.csv")
```

Se não souber por onde começar, algumas perguntas ajudam: tem valor faltando? Tem linha repetida? Tem texto escrito de jeitos diferentes? Tem número que não faz sentido? Tem coluna que não serve para nada?

## Entrega

Mande o link do seu notebook no Colab (com o compartilhamento aberto para quem tiver o link) e o arquivo `imoveis_limpo.csv`. Antes de enviar, rode tudo de novo em Ambiente de execução > Executar tudo, para ver se funciona do começo ao fim.
