# Etapa 5 Busca e triagem dos artigos

## Registro das buscas

| Base | String usada | Data | Filtros | Resultados encontrados | Responsável |
|---|---|---|---|---:|---|
| `[Google Scholar]` |`[("Dijkstra" OR "A-star") AND ("logistics" OR "supply chain") AND ("complexity" OR "execution time")]`| `[1]` | `[01/09/2026]` | `[12]` | `[Júlia, Diana, Gabriela]` |
| `[SciELO]` | `[2]` |`[("Shortest path" OR "route optimization") AND ("heuristic search" OR "informed search") AND ("minimum" OR "lowest cost")]`| `[31/08/2026]` | `[1]` | `[Gabriela]` |
| `[Atlantis Press]` | `[3]` | `[("Graph algorithms" AND "logistics networks") AND ("performance" OR "duration" OR "interval")]` |`[28/08/2026]` | `[5]` | `[Diana]` |
## Resumo da triagem

- Total de resultados encontrados: `[14]`
- Duplicatas removidas: `[3]`
- Artigos avaliados por título e resumo: `[11]`
- Artigos selecionados para leitura completa: `[5]`
- Artigos incluídos no conjunto final: `[1]`

## Decisões

| Artigo | Título e resumo | Texto completo | Motivo da exclusão ou inclusão |
|---|---|---|---|
| `[Ardiansyah et al. (2025)]` | `[Incluir]` | `[Aprovar]` | `[Inclusão: compara diretamente Dijkstra e A* sobre os mesmos dados de uma rede viária urbana, medindo nós explorados e tempo de execução.]` |
| `[Fransen e van Eekelen (2023)]` | `[Incluir]` | `[Aprovar]` | `[Inclusão: trata de planejamento de rotas com A* para veículos guiados automaticamente (logística interna e produção) e mostra como o formato do layout (retangular, hexagonal, arbitrário), o tamanho da grade e a qualidade da heurística afetam o número de iterações.]` |
| `[Lusiani et al. (2021)]` | `[Incluir]` | `[Aprovar]` | `[Inclusão: aplica Dijkstra a um caso real de distribuição logística e mostra o efeito de usar tempo de viagem em vez de distância como peso do grafo.]` |
| `[Rios, Neto e Netto (2016)]` | `[Incluir]` | `[Aprovar]` | `[Inclusão: compara Dijkstra e A* em mapas de grade de tamanhos diferentes e discute a complexidade (mesma ordem no pior caso, com menos operações no A*), o que se liga ao tamanho da rede e à complexidade.]` |
| `[Aldhafferi (2025)]` | `[Incluir]` | `[Aprovar]` | `[Inclusão: é o que responde mais diretamente à pergunta de pesquisa, pois compara Dijkstra, A* e outros algoritmos em grades, grafos aleatórios e grafos livres de escala, medindo tempo, memória e nós expandidos.]` |
| `[Ammar et al. (2016)]` | `[Excluir]` | `[—]` | `[Exclusão: fora do escopo.]` |
| `[Soltani et al. (2002)]` | `[Excluir]` | `[—]` | `[Exclusão: publicado em 2002, anterior ao limite de 2010 definido nos critérios, e não tratado como referência clássica indispensável.]` |
| `[Elshaer et al. (2025)]` | `[Incluir]` | `[Excluir]` | `[Exclusão: texto completo indisponível (acesso pago).]` |
| `[Verma et al. (ano)]` | `[Incluir]` | `[Excluir]` | `[Exclusão: texto completo indisponível.]` |
| `[Candra, Budiman e Hartanto (ano)]` | `[Incluir]` | `[Excluir]` | `[Exclusão: texto completo indisponível (acesso pago).]` |
| `[Chao e Hongxia (ano)]` | `[Incluir]` | `[Excluir]` | `[Exclusão: texto completo indisponível (acesso pago).]` |


## Produto da etapa

1. `[ARDIANSYAH; NASUTION, Abdul Muin; IQBAL, Muhammad. Comparative Analysis of Dijkstra and A* Algorithms for Determining the Shortest Route. Bit-Tech, v. 8, n. 2, p. 2974-2983, 2025. DOI: 10.32877/bt.v8i2.3474.]`
2. `[FRANSEN, Karlijn J. C.; VAN EEKELEN, Joost. Efficient path planning for automated guided vehicles using A* (Astar) algorithm incorporating turning costs in search heuristic. International Journal of Production Research, v. 61, n. 3, p. 707-725, 2023. DOI: 10.1080/00207543.2021.2015806.]`
3. `[LUSIANI, Anie; SARTIKA, Euis; BINARTO, Agus; HABINUDDIN, Endang; AZIS, Irfani. Determination of the Fastest Path on Logistics Distribution by Using Dijkstra Algorithm. In: Proceedings of the 2nd International Seminar of Science and Applied Technology (ISSAT 2021). Advances in Engineering Research, v. 207, p. 246-250, 2021. DOI: 10.2991/aer.k.211106.039.]`
4. `[RIOS, Marcel L.; S. NETO, Francisco S.; NETTO, José F. Magalhães. Análise e Comparação dos Algoritmos de Dijkstra e A-Estrela na Descoberta de Caminhos Mínimos em Mapas de Grade. In: Encontro de Teoria da Computação (ETC), 1., 2016, Porto Alegre. Anais [...]. Porto Alegre: Sociedade Brasileira de Computação, 2016. p. 887-890. DOI: 10.5753/etc.2016.9852.]`
5. `[ALDHAFFERI, Nahier. Time and Memory Trade-Offs in Shortest-Path Algorithms Across Graph Topologies: A*, Bellman-Ford, Dijkstra, AI-Augmented A* and a Neural Baseline. Computers, v. 14, n. 12, art. 545, 2025. DOI: 10.3390/computers14120545.]`

## Checklist

- [X] Todas as buscas possuem data e string.
- [X] As duplicatas foram removidas.
- [X] Os critérios foram aplicados igualmente.
- [X] Toda exclusão possui justificativa.
- [X] Os artigos finais estão diretamente ligados ao problema.
