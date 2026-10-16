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

- - - -

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

- - - -

## Identificação do artigo

- Referência completa: `RIOS, Marcel L.; S. NETO, Francisco S.; NETTO, José F. Magalhães. Análise e Comparação dos Algoritmos de Dijkstra e A-Estrela na Descoberta de Caminhos Mínimos em Mapas de Grade. In: Encontro de Teoria da Computação (ETC), 1., 2016, Porto Alegre. Anais [...]. Porto Alegre: Sociedade Brasileira de Computação, 2016. p. 887–890]`
- DOI ou URL: `[https://doi.org/10.5753/etc.2016.9852]`
- Base de origem: `[Google Scholar]`
- Leitor responsável: `[Gabriela Yuri Kobayashi]`
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
- [ ] Toda citação literal contém

- - - -

## Identificação do artigo

- Referência completa: `[LUSIANI, Anie; SARTIKA, Euis; BINARTO, Agus; HABINUDDIN, Endang; AZIS, Irfani. Determination of the Fastest Path on Logistics Distribution by Using Dijkstra Algorithm. In: Proceedings of the 2nd International Seminar of Science and Applied Technology (ISSAT 2021). Advances in Engineering Research, v. 207, p. 246-250, 2021. DOI: 10.2991/aer.k.211106.039.]`
- DOI ou URL: `[10.2991/aer.k.211106.039]`
- Base de origem: `[Atlantis Press (também disponível no ResearchGate)]`
- Leitor responsável: `[Júlia Moreno da Silva]`
- Data da leitura: `[10/10/2026]`

## Fichamento

### Problema investigado

`[A distribuição logística da Bulog (Java Ocidental, Indonésia) sofre atrasos por congestionamento em algumas áreas, e o caminho mais curto em distância nem sempre é o mais rápido. Os autores querem saber qual é o caminho mais rápido entre dois armazéns da Bulog usando o tempo de viagem, e não a distância, como peso do grafo (p. 246-247).]`

### Objetivo do estudo

`[Determinar o caminho mais rápido do armazém Bulog Cibitung (Bekasi) ao armazém Bulog Bojong (Cianjur) aplicando o algoritmo de Dijkstra, de forma manual e também em Matlab, sobre um grafo ponderado conexo cujo peso é o tempo de viagem.]`

### Método utilizado

- A rede é modelada como grafo ponderado conexo, não direcionado, com 8 vértices (áreas de passagem, do armazém de Cibitung ao de Bojong) e 16 arestas. O peso de cada aresta é o tempo de viagem em minutos (Tabela 1).
- Dijkstra em três passos: marca a origem como visitada, atualiza o peso dos vértices adjacentes (de "não encontrado" para "encontrado") e visita o de menor peso. Repete até o destino (vértice 8) ser visitado.
- Execução manual (Tabelas 2 a 5 e Figuras 3 a 6), conferida em Matlab com a matriz de adjacência do grafo (Figura 7).
- Como segunda verificação, os autores citam o resultado do algoritmo de Prim sobre os mesmos dados, publicado em outro trabalho deles (ref. [11], em indonésio).

### Contexto, amostra ou dados

- É um único par origem-destino, de Bekasi a Cianjur, em Java Ocidental.
- Os tempos de viagem vêm do escritório da Bulog em Java Ocidental e do Google Maps, coletados durante a pandemia de Covid-19.
- Os pesos são estáticos (um valor por aresta, sem variação por horário ou trânsito).
- O artigo não informa como o Google Maps foi consultado (horário, tipo de veículo).

### Principais resultados

`[O caminho mais rápido é Cibitung – Cikampek – Sadang (Purwakarta) – Cikalong – Cipatat – Cianjur (vértices 1-2-4-6-7-8), com 154 minutos. O Matlab dá o mesmo resultado do cálculo manual. Segundo os autores, o algoritmo de Prim, com os mesmos dados, também chegou aos 154 minutos, e eles concluem que o Dijkstra está confirmado como método de otimização de rotas (p. 249-250).]`

### Limitações apresentadas

`[O artigo não tem seção de limitações e não as discute. As fragilidades observadas estão no comentário crítico.]`

### Contribuição para o nosso artigo

`[É um exemplo aplicado de Dijkstra em logística real (distribuição da Bulog). Mostra que o caminho mais curto passa a ser o mais rápido apenas trocando o peso do grafo de distância para tempo, o que ajuda a discutir a escolha da métrica de custo. Não compara com o A*, então serve de base para o Dijkstra e não para a comparação entre os algoritmos.]`

### Comentário crítico

`[Pontos fortes: método didático, com todos os pesos publicados (Tabela 1) e o passo a passo em tabelas, o que permite replicar. Conferi o resultado: 41 + 13 + 45 + 33 + 22 = 154 minutos, e a alternativa 1-3-5-8 daria 194. Pontos fracos: o grafo é pequeno, há um único par origem-destino, não há comparação com outro algoritmo de caminho mínimo (A*, Bellman-Ford) nem medição de tempo de execução. A validação com Prim é frágil: o Prim clássico resolve árvore geradora mínima, não caminho mínimo, o artigo não explica a adaptação e só cita o resultado. A motivação é o congestionamento, mas os pesos são estáticos e foram coletados na pandemia, o que pode não refletir o tráfego normal. O texto também afirma que o algoritmo acha o caminho mínimo entre quaisquer dois vértices, quando o Dijkstra resolve a partir de uma origem por vez.]`

## Checklist

- [X] O artigo foi lido além do resumo.
- [X] O método e os resultados foram identificados.
- [X] As limitações foram registradas.
- [X] A conexão com o tema foi explicada.
- [ ] Toda citação literal contém página.

- - - -

## Identificação do artigo

- Referência completa: `[ALDHAFFERI, Nahier. Time and Memory Trade-Offs in Shortest-Path Algorithms Across Graph Topologies: A*, Bellman-Ford, Dijkstra, AI-Augmented A* and a Neural Baseline. Computers, v. 14, n. 12, art. 545, 2025. DOI: 10.3390/computers14120545.]`
- DOI ou URL: `[10.3390/computers14120545]`
- Base de origem: `[MDPI (acesso aberto)]`
- Leitor responsável: `[Júlia Moreno da Silva]`
- Data da leitura: `[10/10/2026]`

## Fichamento

### Problema investigado

`[O desempenho prático dos algoritmos de caminho mínimo depende da topologia do grafo, da densidade, da distribuição dos pesos e da implementação, e não só da complexidade teórica. Também não está claro em que condições métodos aprendidos (redes neurais) superam algoritmos clássicos bem ajustados. A pergunta central é como estimativas de distância aprendidas por modelos de machine learning afetam o compromisso entre tempo, memória e qualidade da solução dos algoritmos clássicos em diferentes topologias (Seção 1).]`

### Objetivo do estudo

`[Comparar Dijkstra, A*, Bellman-Ford, A* com heurística aprendida (AI-Augmented A*) e um modelo neural de referência quanto a tempo de execução, pico de memória e nós expandidos, em grades, grafos aleatórios e grafos livres de escala, com um protocolo reprodutível. O autor declara que não propõe um novo algoritmo, e sim uma caracterização empírica.]`

### Método utilizado

- Problema de menor caminho entre um par origem-destino, em grafos com pesos não negativos, Uniform(1, 10).
- Três famílias de grafos: grade de 4 vizinhos (A* com distância de Manhattan), Erdős-Rényi (p = 8/n) e livre de escala de Barabási-Albert (m = 4). Nas duas últimas o A* usa heurística nula, o que o torna equivalente ao Dijkstra.
- Várias instâncias independentes e pares origem-destino aleatórios por configuração, com sementes fixas. Os resultados são medianas, com IQR e desvio padrão, e comparações pareadas.
- Implementação em Python (NetworkX, heapq), sem otimizações de baixo nível. Tempo medido com timer monotônico e memória com psutil e memory_profiler.
- Heurística aprendida: Gradient Boosting Regressor (grau e coeficiente de agrupamento do nó atual e do alvo) e GNN, treinados com distâncias calculadas pelo Dijkstra. Para evitar superestimação, usa h_α = α·h, com α = 0,2 no caso Erdős-Rényi.
- Testes de robustez: grafos mais densos, ruído multiplicativo de 0,9 a 1,1 nos pesos e testes com pesos negativos para o Bellman-Ford.

### Contexto, amostra ou dados

- Dados sintéticos, sem redes reais (nem viárias).
- Tamanhos: n ∈ {200, 400, 600, 1600} na metodologia. O resumo fala em grades e grafos aleatórios de 100 e 1000 nós e em até 103.103 nós (inconsistência, ver comentário crítico).
- O A* com heurística aprendida é avaliado principalmente em grafos Erdős-Rényi com n = 600.
- O número de instâncias por configuração aparece só como "K", sem valor.
- Hardware informado no resumo: Intel Xeon Gold 6248R, NVIDIA Tesla V100 (32 GB), 256 GB de RAM, Ubuntu 20.04. A GPU é usada só na inferência neural.

### Principais resultados

`[Com pesos não negativos, Dijkstra, A* e Bellman-Ford encontram sempre o mesmo custo (Seção 4.1). O A* só leva vantagem quando a heurística é informativa: em grades (Manhattan) reduz as expansões, e em grafos aleatórios e livres de escala (h = 0) equivale ao Dijkstra. O Bellman-Ford é o mais lento e o que mais consome memória, enquanto Dijkstra e A* têm memória semelhante. O resumo reporta A* de 1,37 a 1,91 vezes mais rápido que o Dijkstra e Bellman-Ford de 1,50 a 1,92 vezes mais lento. O A* com heurística aprendida manteve a otimalidade após a calibração, mas, em Erdős-Rényi com n = 600, não ficou mais rápido que o Dijkstra nem que o A* com heurística nula (Seção 4.4). O regressor neural isolado teve baixo poder preditivo (R² próximo de zero). A conclusão é: A* quando há boa heurística, Dijkstra como base robusta sem heurística, Bellman-Ford para pesos negativos, e IA como apoio à heurística, não como substituta do algoritmo exato.]`

### Limitações apresentadas

- Implementação em Python não otimizada: os tempos absolutos podem não valer para implementações compiladas ou com GPU (Seção 5.7).
- Escala pequena (centenas de nós), sem estudo de escalabilidade em grafos grandes.
- Características do modelo de IA só locais (grau e agrupamento), o que limita o poder preditivo em grafos aleatórios. Os ganhos da IA ficam restritos a um cenário (Erdős-Rényi, n = 600).
- O autor não afirma admissibilidade universal da heurística aprendida, só que não observou violações nos testes.
- A inferência do modelo tem custo que pode anular a redução de expansões em grafos pequenos.

### Contribuição para o nosso artigo

`[É evidência recente (dez/2025) de que o A* só supera o Dijkstra quando existe uma heurística informativa (por exemplo, geométrica em grades). Sem ela, os dois se equivalem, e ambos retornam o mesmo caminho ótimo. Apoia a ideia de que o ganho do A* depende da heurística e da topologia, e traz o Bellman-Ford como contraponto para pesos negativos. Redes viárias se parecem mais com as grades do estudo, mas o artigo não testa redes reais.]`

### Comentário crítico

`[Pontos fortes: protocolo explícito e justo (mesmas entradas e critério de parada, medianas com IQR, sementes fixas, otimalidade checada contra o Dijkstra), três topologias, memória medida além do tempo, e o autor admite que o trabalho é empírico. Pontos fracos: há contradições internas, e os números do resumo não batem com o corpo do texto. O resumo diz que o A* é 1,37 a 1,91 vezes mais rápido que o Dijkstra, mas a Seção 4 diz que os tempos são quase idênticos em Erdős-Rényi e livre de escala, e que mesmo na grade o ganho foi mascarado pelo overhead do Python (4.2). O resumo dá o Bellman-Ford de 1,5 a 1,9 vezes mais lento, e a Seção 4 diz que é cerca de uma ordem de grandeza. Os tamanhos de grafo também mudam entre resumo, metodologia e resultados. A Seção 4.4 diz que o A* com IA ficou mais lento que o Dijkstra em Erdős-Rényi, mas as Seções 5.4 e 6 falam em menor tempo, menor memória e "ganhos mais substanciais". Os resultados em grade com IA foram omitidos "por brevidade" e mesmo assim sustentam a conclusão. O hardware é descrito de forma diferente no resumo e na Seção 3.3. A IA é testada onde não há heurística geométrica e com características fracas, então "IA não competitiva" vale só para esse modelo simples. Há erros de referência (Dijkstra, de 1959, aparece como 2022; um artigo de neuroimagem sustenta a afirmação sobre algoritmos clássicos). Tabelas e figuras não foram conferidas nesta leitura, então convém checar os fatores de aceleração antes de citá-los, preferindo a Seção 4 ao resumo.]`

## Checklist

- [X] O artigo foi lido além do resumo.
- [X] O método e os resultados foram identificados.
- [X] As limitações foram registradas.
- [X] A conexão com o tema foi explicada.
- [ ] Toda citação literal contém página.
