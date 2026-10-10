# Etapa 6 Leitura e fichamento

## Identificação do artigo

- Referência completa: `[ARDIANSYAH; NASUTION, Abdul Muin; IQBAL, Muhammad. Comparative Analysis of Dijkstra and A* Algorithms for Determining the Shortest Route. Bit-Tech, v. 8, n. 2, p. 2975-2983, 2025. DOI: 10.32877/bt.v8i2.3474.]`
- DOI ou URL: `[10.32877/bt.v8i2.3474]`
- Base de origem: `[ResearchGate]`
- Leitor responsável: `[Diana Kellen de Almeida Malaquias]`
- Data da leitura: `[05/10/2026]`

## Fichamento

### Problema investigado

`[Dijkstra garante o caminho ótimo, mas ele explora o grafo de forma exaustiva e esse custo cresce com redes urbanas maiores. O A* usa uma heurística para reduzir a exploração. Os autores desse artigo querem saber se em um mesmo cenário urbano e com os mesmos dados, o A* é de fato mais eficiente que o Dijkstra sem perder a otimalidade.]`

### Objetivo do estudo

`[Comparar Dijkstra e A* na determinação da rota mais curta numa rede viária urbana (de SMKN 9 Medan até Gramedia Gajah Mada, Indonésia). Os critérios são otimalidade da rota, eficiência computacional e número de nós explorados.]`

### Método utilizado

- A rede viária é modelada como grafo ponderado com 7 nós (A a G) e 11 arestas.
- Dijkstra usa relaxamento de arestas, d(v) = min(d(v), d(u) + w(u,v)). O A* usa f(n) = g(n) + h(n).
- Os dois algoritmos rodam sobre os mesmos dados.
- Cálculo manual (Tabelas 4 e 5) e implementação em Python para medir nós explorados e tempo.

### Contexto, amostra ou dados

- É um único par origem-destino em Medan.
- Os pesos das arestas g(n), em km, são de estimativas do Google Maps.
- A heurística h(n) são distâncias em linha reta de cada nó ao destino, também medidas no Google Maps.
- Os pesos são estáticos (sem trânsito).

### Principais resultados

`[Os dois algoritmos encontram a mesma rota ótima, A–B–E–G com 5,7 km. O A* é mais eficiente nos dois conjuntos de números do artigo. Os autores concluem que o Dijkstra serve para redes pequenas e o A* para navegação em redes grandes, onde eficiência e escalabilidade importam.]`

### Limitações apresentadas

- O grafo é muito pequeno e a diferença de tempo pode refletir o overhead do Python e a máquina usada, os resultados podem não generalizar para redes urbanas grandes.
- Os dados do Google Maps podem divergir do comportamento real de viagem.
- Os pesos são estáticos, sem congestionamento, incidentes ou semáforos.

### Contribuição para o nosso artigo

`[É evidencia recente (2025) de que Dijkstra e A* retornam o mesmo caminho ótimo, e de que o A* o faz com menos exploração, é um bom apoio para a comparação entre os algoritmos]`

### Comentário crítico

`[Metodologia simples e transparente, com dados e tabelas replicáveis, comparação justa (mesmo grafo e mesmos dados) e as limitações são reconhecidas na discussão. Tabela 4 (Dijkstra) contradiz a própria fórmula de relaxamento, na linha de E, o valor de F passa de 4,5 para 4,7, na linha de F, G vira 6,2 (o correto seria 6,0) e na linha de D, G vira 5,8, embora já fosse 5,7, a tabela termina em 5,8, e o texto diz 5,7.]`

## Checklist

- [X] O artigo foi lido além do resumo.
- [X] O método e os resultados foram identificados.
- [X] As limitações foram registradas.
- [X] A conexão com o tema foi explicada.
- [ ] Toda citação literal contém página.

-----

## Identificação do artigo

- Referência completa: `[FRANSEN, Karlijn; VAN EEKELEN, Joost. Efficient path planning for automated guided vehicles using A* (Astar) algorithm incorporating turning costs in search heuristic. International Journal of Production Research, v. 61, n. 3, p. 707-725, 2023. DOI: 10.1080/00207543.2021.2015806.]`
- DOI ou URL: `[10.1080/00207543.2021.2015806]`
- Base de origem: `[ResearchGate]`
- Leitor responsável: `[Diana Kellen de Almeida Malaquias]`
- Data da leitura: `[05/10/2026]`

## Fichamento

### Problema investigado

`[Em sistemas de AGVs (veículos guiados automaticamente), o caminho de menor custo num grafo geométrico deve considerar o tempo gasto em curvas, porque o veículo precisa frear, girar e acelerar. A literatura sobre A* tem duas lacunas: a maioria das heurísticas não inclui o custo de giro, ou só funciona em estruturas específicas de grafo (em geral grades ortogonais); nenhum dos trabalhos revisados traz prova de admissibilidade da heurística.]`

### Objetivo do estudo

`[Propor uma heurística para o A* que inclua custos de giro, seja admissível e monótona (garantindo o caminho ótimo e a expansão de cada vértice no máximo uma vez), funcione em qualquer grafo geométrico e reduza o número de iterações necessárias.]`

### Método utilizado

- Heurística h = h_trans + h_rot:
 - h_trans = distância euclidiana ÷ velocidade máxima do AGV;
 - h_rot = custo de giro por radiano × limite inferior do ângulo mínimo de rotação (soma de três ângulos, θ1 + mín(θ2 + θ3)).
- Provas formais de monotonicidade (Apêndice 2) e admissibilidade (Apêndice 3).
- Estudo comparativo numérico: número de iterações do A* para todos os pares origem-destino de cada layout, comparando com Bae e Chung (2018, igual a Bae e Chung 2019 e Lian e Xie 2019) e uma versão modificada de Cui et al. (2018).
- Métrica (Eq. 17): número médio ponderado de iterações por elemento do caminho. O valor ideal é 1.

### Contexto, amostra ou dados

- Dados sintéticos, sem casos reais.
- Layouts retangulares, hexagonais e arbitrários de aproximadamente 10×10 a 40×40 elementos.
- Cenários com 0% e 20% dos elementos bloqueados. Nos bloqueados foram geradas 40 combinações aleatórias para calcular intervalos de confiança de 95%.
- Parâmetros base (Tabela 2): velocidade máxima de 2 m/s, elemento de grade de 2 m, velocidade de rotação máxima de π/2 rad/s.
- Varredura de parâmetros (Fig. 7): rotação de π/4 a π rad/s e translação de 0,5 a 5 m/s, numa grade retangular 30×30 sem bloqueios.

### Principais resultados

`[A heurística proposta exige em média o menor número de iterações em todas as topologias. Em seguida vêm a versão modificada de Cui et al. (só em grades retangulares) e a de Bae e Chung. As diferenças entre heurísticas ficam aproximadamente constantes com o tamanho da grade (Fig. 6). Redução de até 68% no número médio ponderado de iterações, dependendo dos parâmetros (p. 14). O ganho cresce quando a velocidade de rotação é menor e a de translação é maior. Quando a rotação é muito rápida ou o custo de giro é baixo, todas as heurísticas se comportam de forma parecida. Em grades retangulares, a heurística de Cui et al. pode vencer em pares específicos (origem-destino quase alinhados a um eixo), mas perde na média.]`

### Limitações apresentadas

`[A heurística exige mais operações para ser calculada. Os autores sugerem pré-computação, e o custo extra pode não compensar se o custo de giro for zero. Desacelerações e acelerações antes e depois da curva não são modeladas explicitamente.]`

### Contribuição para o nosso artigo

`[Mostra que caminho mais curto nem sempre é o mais eficiente na prática, porque as curvas custam tempo, vínculo com logística.]`

### Comentário crítico

`[Provas completas de admissibilidade e monotonicidade, raras nos trabalhos da área, como os próprios autores observam, comparação justa: todas as heurísticas encontram o mesmo caminho ótimo, e as concorrentes foram adaptadas para operar sob as mesmas condições. Mede só iterações, não tempo de execução, só dados sintéticos e um único veículo, sem tráfego, congestionamento ou frota. Isso limita a conclusão para logística de larga escala, embora o artigo cite congestionamento como motivação.]`

## Checklist

- [X] O artigo foi lido além do resumo.
- [X] O método e os resultados foram identificados.
- [X] As limitações foram registradas.
- [X] A conexão com o tema foi explicada.
- [ ] Toda citação literal contém página.

-----

artigo 3 e 4 da júlia (AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaQUIIIII)

-----

## Identificação do artigo

- Referência completa: `RIOS, Marcel L.; S. NETO, Francisco S.; NETTO, José F. Magalhães. Análise e Comparação dos Algoritmos de Dijkstra e A-Estrela na Descoberta de Caminhos Mínimos em Mapas de Grade. In: Encontro de Teoria da Computação (ETC), 1., 2016, Porto Alegre. Anais [...]. Porto Alegre: Sociedade Brasileira de Computação, 2016. p. 887–890]`
- DOI ou URL: `[https://doi.org/10.5753/etc.2016.9852]`
- Base de origem: `[Google Scholar]`
- Leitor responsável: `[Gabriela]`
- Data da leitura: `[08/10/2026]`

## Fichamento

### Problema investigado

`[A necessidade de encontrar caminhos mínimos de forma eficiente, comparando o comportamento e a complexidade dos algoritmos Dijkstra e A* em mapas de grade]`

### Objetivo do estudo

`Analisar e comparar a eficiência e a complexidade dos algoritmos Dijkstra e A* na busca de caminhos mínimos]`

### Método utilizado

`[Os autores analisaram os algoritmos, apresentaram seus pseudocódigos e realizaram experimentos em mapas de grade de diferentes tamanhos. O A* utilizou a heurística da distância de Manhattan]`

### Contexto, amostra ou dados

`[Foram utilizados mapas de grade com custos uniformes e movimentos horizontais e verticais. Os experimentos incluíram um mapa 7×7 e comparações em grades de diferentes tamanhos]`

### Principais resultados

`[O A* apresentou maior eficiência que o Dijkstra, realizando menos operações para encontrar o caminho mínimo. Apesar disso, os autores apontaram que ambos possuem a mesma ordem de complexidade de tempo no pior caso]`

### Limitações apresentadas

`[O estudo utiliza mapas de grade com custos uniformes e uma heurística específica. Não apresenta experimentos com redes logísticas reais nem uma avaliação detalhada do consumo de memória]`

### Contribuição para o nosso artigo

`[Ajuda a compreender como Dijkstra e A* se comportam em redes de diferentes tamanhos e como a heurística pode melhorar a eficiência da busca. Serve de base para comparar o desempenho dos algoritmos em redes logísticas]`

### Comentário crítico

`[O estudo apresenta uma comparação direta entre os algoritmos e demonstra a vantagem da heurística do A*. Entretanto, os experimentos em grades simples limitam a aplicação direta dos resultados a redes logísticas reais, que podem apresentar diferentes distâncias, custos e estruturas]`

## Checklist

- [x] O artigo foi lido além do resumo.
- [x] O método e os resultados foram identificados.
- [x] As limitações foram registradas.
- [x] A conexão com o tema foi explicada.
- [ ] Toda citação literal contém página.

-----

## Identificação do artigo

- Referência completa: `[ALDHAFFERI, Nahier. Time and Memory Trade-Offs in Shortest-Path Algorithms Across Graph Topologies: A*, Bellman–Ford, Dijkstra, AI-Augmented A* and a Neural Baseline. Computers, v. 14, n. 12, artigo 545, 2025]`
- DOI ou URL: `[https://doi.org/10.3390/computers14120545]`
- Base de origem: `[Google Scholar]`
- Leitor responsável: `[Gabriela]`
- Data da leitura: `[09/10/2006]`

## Fichamento

### Problema investigado

`[Como o tamanho e a estrutura dos grafos influenciam o tempo de execução, o consumo de memória e a eficiência dos algoritmos de caminho mínimo]`

### Objetivo do estudo

`[Comparar o desempenho dos algoritmos Dijkstra, A*, Bellman-Ford e métodos com inteligência artificial, analisando tempo, memória e quantidade de nós explorados em diferentes grafos]`

### Método utilizado

`[O autor realizou experimentos computacionais utilizando grafos de diferentes tamanhos e estruturas. Os algoritmos foram executados repetidamente nas mesmas condições, comparando tempo de execução, consumo de memória e nós explorados. O A* utilizou heurísticas para orientar a busca, enquanto o Dijkstra considerou os custos acumulados dos caminhos]`

### Contexto, amostra ou dados

`[Foram utilizados grafos gerados computacionalmente, incluindo grades, grafos aleatórios e grafos livres de escala, com diferentes tamanhos e pesos nas conexões]`

### Principais resultados

`[O A* explorou menos nós e apresentou vantagens de desempenho em grafos estruturados, especialmente quando utilizou uma heurística adequada. Em grafos sem uma heurística eficiente, seu desempenho foi semelhante ao do Dijkstra. O consumo de memória dos dois algoritmos também foi parecido em diversos experimentos]`

### Limitações apresentadas

`[Os experimentos foram realizados principalmente com grafos gerados artificialmente e implementações em Python sem otimizações avançadas. Por isso, os resultados podem ser diferentes em redes logísticas reais ou em sistemas maiores]`

### Contribuição para o nosso artigo

`[O estudo ajuda a responder como o tamanho e a estrutura das redes influenciam o desempenho de Dijkstra e A*. Também demonstra que a eficiência do A* depende da qualidade da heurística utilizada, o que é importante para sua aplicação em redes logísticas]`

### Comentário crítico

`[O artigo apresenta uma comparação abrangente, considerando tempo, memória e diferentes estruturas de grafos. Seu ponto forte é demonstrar que o A* nem sempre supera o Dijkstra. Entretanto, a ausência de testes específicos em redes logísticas reais limita a aplicação direta dos resultados ao contexto de entregas]`

## Checklist

- [x] O artigo foi lido além do resumo.
- [x] O método e os resultados foram identificados.
- [x] As limitações foram registradas.
- [x] A conexão com o tema foi explicada.
- [ ] Toda citação literal contém página.
