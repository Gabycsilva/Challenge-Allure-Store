# Challenger1_alura-store-analysis
Análise de Eficiência da Rede Alura Store: Este repositório contém um notebook e README para análise de 4 lojas fictícias da Alura Store. Avaliamos faturamento, avaliações de clientes, frete médio e demanda por produtos, recomendando qual loja vender para otimizar recursos e maximizar eficiência. 🚀

# Importação e Consolidação dos Dados

Nesta etapa, carregamos os dados das quatro lojas utilizando a biblioteca **pandas** e os consolidamos em um único DataFrame. Isso permite realizar análises globais de forma eficiente.

### Passos Realizados:
1. Importamos os dados de cada loja com `pd.read_csv()`.
2. Concatenamos todos os DataFrames em um único DataFrame usando `pd.concat()`, ignorando os índices para evitar inconsistências.
3. Exibimos uma amostra dos dados consolidados para validar o carregamento correto.

## Criação da Coluna 'Faturamento'

A coluna **'Faturamento'** foi criada para representar o valor total das vendas, calculado como o produto entre as colunas **'Vendas'** e **'Preco'**.

### Passos Realizados:
1. Verificamos se a coluna 'Faturamento' já existia no DataFrame.
2. Caso não estivesse presente, verificamos a existência das colunas necessárias ('Vendas' e 'Preco') para realizar o cálculo.
3. Multiplicamos as colunas **'Vendas'** e **'Preco'** para criar a nova coluna **'Faturamento'**.

#### Observação:
Se uma das colunas necessárias não estivesse presente, o código retornaria uma mensagem de erro informando sobre a ausência dos dados essenciais.

# Faturamento Total por Loja

Após criar a coluna **'Faturamento'**, agrupamos os dados pela coluna **'Loja'** para calcular o faturamento total de cada loja.

### Passos Realizados:
1. Usamos o método `.groupby()` para agrupar os dados por loja e calcular a soma do faturamento total.
2. Exibimos os resultados tabulares para validar os cálculos.
3. Geramos um gráfico de barras estilizado com **Seaborn**, utilizando a paleta de cores **Blues_d** para representar os valores do faturamento.

#### Detalhes do Gráfico:
- **Eixo X**: Nomes das lojas.
- **Eixo Y**: Valor total de faturamento por loja.


- # Vendas Totais por Categoria: Análise Detalhada

Nesta etapa, exploramos os dados do DataFrame consolidado para identificar as vendas totais por categoria e apresentá-las em um gráfico de barras estilizado.

---

## 1. Verificação das Colunas

Antes de iniciar a análise, verificamos as colunas disponíveis no DataFrame consolidado para garantir que as informações necessárias estão presentes. As colunas essenciais para esta etapa incluem:
- **Categoria do Produto**: Representa os grupos de produtos vendidos.
- **Preço**: Indica o valor de cada produto vendido.

Caso alguma coluna importante estivesse ausente, o código retornaria uma mensagem informando a indisponibilidade e interromperia a execução.

---

## 2. Cálculo das Vendas Totais por Categoria

Agrupamos os dados pela coluna **'Categoria do Produto'** e somamos os valores da coluna **'Preço'** para determinar o volume financeiro total de vendas em cada categoria.

### Passos Realizados:
- Utilizamos o método `.groupby()` para agrupar os dados por categoria.
- Calculamos a soma dos valores de **'Preço'** em cada grupo, resultando no total de vendas por categoria.
- Exibimos os resultados tabulares para validar os cálculos e identificar categorias com maior ou menor desempenho financeiro.

---

## 3. Visualização Gráfica com Paleta de Cores

Para facilitar a interpretação dos dados, criamos um gráfico de barras utilizando a biblioteca **Seaborn**. Cada categoria foi representada por uma barra colorida, destacando seu volume financeiro.

### Detalhes do Gráfico:
- **Eixo X**: Mostra os nomes das categorias de produto.
- **Eixo Y**: Apresenta o valor total das vendas por categoria.
- **Estilo e Personalização**:
  - Barras coloridas utilizando a paleta **Spectral**, proporcionando clareza visual.
  - Adicionamos uma grade leve no eixo Y para facilitar a leitura dos valores.
  - Ajustamos títulos, rótulos e layout para melhorar a organização e visualização do gráfico.

---

### Conclusão:
Com esta análise, foi possível identificar as categorias com maior e menor volume de vendas, permitindo insights sobre os produtos mais rentáveis. A visualização gráfica torna essa informação mais acessível para análises rápidas e estratégicas.

# Avaliação das Lojas: Análise e Visualização

Nesta seção, exploramos os dados de avaliações dos clientes para calcular a **média de avaliação por loja** e apresentamos os resultados com um gráfico tipo pizza.

---

## 1. Limpeza e Preparação dos Dados

Antes de realizar os cálculos, garantimos que os dados da coluna **'Avaliação da compra'** fossem válidos:
- **Conversão de Dados**: Transformamos os valores da coluna em números, substituindo entradas inválidas por NaN.
- **Remoção de Dados Inválidos**: Excluímos todos os registros onde os valores de **'Avaliação da compra'** estavam ausentes ou inválidos.

Esses passos garantiram a consistência e a precisão dos dados para análise.

---

## 2. Cálculo da Média de Avaliação

Agrupamos os dados pela coluna **'Loja'** e calculamos a média das avaliações para cada loja:
- Utilizamos o método `.groupby()` para organizar os dados por loja.
- O cálculo da média foi realizado utilizando o método `.mean()`.

Essa análise destaca as lojas com maior e menor nível de satisfação dos clientes.

---

## 3. Visualização: Gráfico Tipo Pizza

Para apresentar os resultados de maneira clara e intuitiva, utilizamos um gráfico tipo pizza.

**Detalhes do Gráfico**:
- **Setores**: Representam a média de avaliação para cada loja.
- **Rótulos**: Identificam as lojas diretamente no gráfico.
- **Porcentagens**: Mostram a participação relativa de cada loja em termos de média de avaliação.
- **Cores**: Utilizamos a paleta **coolwarm** para diferenciar as lojas e melhorar a experiência visual.

---

## Conclusão

A análise revelou as médias de avaliação de cada loja, oferecendo insights importantes sobre a percepção dos clientes. Lojas com avaliações mais altas refletem maior satisfação, enquanto lojas com médias menores podem indicar a necessidade de melhorias no atendimento ou nos serviços oferecidos. Essa visualização proporciona uma base sólida para ações estratégicas voltadas à experiência do cliente.

# Análise dos Produtos Mais e Menos Vendidos

Nesta etapa, identificamos os produtos mais vendidos e menos vendidos, com base no valor total das vendas, e visualizamos os resultados utilizando gráficos interativos.

---

## 1. Verificação das Colunas

Primeiramente, garantimos que as colunas necessárias estão presentes no DataFrame:
- **Produto**: Representa os diferentes itens vendidos.
- **Preço**: Indica o valor de cada venda.

Caso uma dessas colunas esteja ausente, o código interrompe a execução e exibe uma mensagem informando a indisponibilidade.

---

## 2. Cálculo das Vendas Totais por Produto

Agrupamos os dados pela coluna **'Produto'** e somamos os valores de **'Preço'** para determinar o total de vendas de cada produto.

### Passos Realizados:
1. Utilizamos o método `.groupby()` para agrupar os dados por produto.
2. Calculamos a soma dos valores de **'Preço'** dentro de cada grupo.
3. Ordenamos os produtos por valor total de vendas, tanto em ordem decrescente quanto crescente, para identificar os mais vendidos (Top 5) e os menos vendidos (Bottom 5).

---

## 3. Visualização Gráfica Interativa

Criamos dois gráficos interativos para apresentar os produtos mais vendidos e menos vendidos, utilizando a biblioteca **Plotly Express**.

### Detalhes dos Gráficos:
- **Gráfico 1: Produtos Mais Vendidos**
  - Exibe os 5 produtos com maior valor total de vendas.
  - Eixo X: Nome do produto.
  - Eixo Y: Valor total das vendas.
  - Personalização: Cores distintas atribuídas a cada produto.

- **Gráfico 2: Produtos Menos Vendidos**
  - Exibe os 5 produtos com menor valor total de vendas.
  - Eixo X: Nome do produto.
  - Eixo Y: Valor total das vendas.
  - Personalização: Cores distintas atribuídas a cada produto.

Ambos os gráficos foram ajustados com rótulos claros, títulos descritivos e interatividade para facilitar a análise.

---

### Conclusão:

Com base nesta análise, conseguimos identificar os produtos mais e menos rentáveis, oferecendo insights valiosos para decisões estratégicas, como otimização do mix de produtos e definição de promoções.

# Frete Médio por Loja: Análise e Visualização

Nesta seção, exploramos os dados de frete para calcular o **frete médio por loja** e apresentamos os resultados utilizando um gráfico de dispersão.

---

## 1. Cálculo do Frete Médio por Loja

Para determinar o frete médio por loja, agrupamos os dados pela coluna **'Loja'** e calculamos a média dos valores da coluna **'Frete'**:
- Utilizamos o método `.groupby()` para organizar os dados por loja.
- O método `.mean()` foi aplicado para calcular o valor médio de frete em cada grupo.

Essa análise permite identificar variações nos custos de entrega entre diferentes lojas.

---

## 2. Visualização: Gráfico de Dispersão

O gráfico de dispersão foi escolhido para representar os resultados de forma clara e compacta.

**Detalhes do Gráfico**:
- **Eixo X**: Exibe os nomes das lojas.
- **Eixo Y**: Representa o valor médio do frete de cada loja.
- **Estilo e Personalização**:
  - Cada ponto no gráfico representa o frete médio de uma loja.
  - Ajustamos o tamanho do gráfico para ser pequeno e compacto (`figsize=(6, 4)`).
  - Utilizamos uma grade leve no eixo Y para facilitar a leitura.

---

## Conclusão

Esta visualização destaca as lojas com maiores e menores custos médios de entrega. As informações obtidas podem ser usadas para otimizar os custos logísticos e definir estratégias de precificação mais eficazes, beneficiando tanto os negócios quanto os consumidores.


# Solicitação para pressionar Enter
input("Para gerar o relatório: Pressione (Enter)")

# Exibe o relatório após Enter
print(relatorio)
- **Estilo**: Grades leves no eixo Y e paleta gradiente azul para as barras, proporcionando clareza e elegância à visualização.

- - relatorio = """
Análise de Eficiência da Rede Alura Store
------------------------------
📄 Relatório Final:

✅ Objetivo
O objetivo deste relatório é analisar as quatro lojas fictícias da Alura Store com base nos dados de vendas, desempenho e avaliações. Com isso, identificamos a loja com menor eficiência para recomendar ao Senhor João qual loja vender, permitindo iniciar um novo empreendimento e maximizar seus recursos.

📊 Critérios Analisados
1️⃣ Faturamento por Categoria
2️⃣ Média de Avaliação das Lojas
3️⃣ Produtos Mais e Menos Vendidos
4️⃣ Frete Médio por Loja

🛠 Identificação da Loja com Menor Eficiência
Baseado nos dados apresentados, identificamos qual loja está abaixo do padrão em desempenho e competitividade.

⭐ Recomendação Final
Recomendamos que o Senhor João venda a Loja 1 para financiar seu novo empreendimento. Essa decisão se apoia em dados como menor avaliação de clientes, maiores custos logísticos, e oportunidades limitadas de crescimento sustentável.

📈 Oportunidade Estratégica
A venda da Loja 1 permitirá que o Senhor João:
✔️ Reforce lojas com melhor desempenho e satisfação.
✔️ Expanda categorias de maior demanda, como eletrônicos.
✔️ Otimize a experiência do cliente com foco em eficiência.

Com essa estratégia, o Senhor João estará bem-posicionado para alcançar sucesso em seu novo empreendimento, fortalecendo sua rede Alura Store! 🚀
------------------------------
