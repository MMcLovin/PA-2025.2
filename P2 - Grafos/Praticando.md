#  Kosaraju's Algorithm (Strongly Connected Components)

## Grafo (Esse na real já é o reverso, peguei por engano kkkkk)
![grafo_inicial_kosaraju](/P2%20-%20Grafos/me%20de%20ibagens/Aula%2011%20-%20SCC2.png)

## Execução

1. Rode a DFS até o final (anotando pré e post).
    - Vc vai começar de um nó aleatório e vai seguir os vizinhos dele e depois os vizinhos dos vizinhos e assim por diante. Chegou num beco sem saída? Backtracking (aqui a gnt começa a anotar os posts) para quem chamou aquele nó. LEMBRANDO, se um nó ainda tem vizinhos que podem ser visitados, ELE NÃO RECEBE um post.
2. Selecione o v com o maior post(v).
3. Faça o Grev.
4. Rode uma DFS em Grev a partir do nó de maior post em 2.
4. Pegue o SCC identificado e abstraia do Grev.
    - A DFS no Grev nos garante que a DFS NUNCA vai "vazar"
5. Ainda há nós? Olhe para o G resultante da DFS com os POSTs e pule para o `2.`.
6. That's all, folks.

# Djikstra's Algorithm (Shortest/Cheapest Path)

![grafo_inicial_dijkstra](/P2%20-%20Grafos/me%20de%20ibagens/Aula%2012%20-%20Dijkstra.png)

## Execução

# Prim's Algorithm (Minimum Spanning Tree)

![grafo_inicial_prim](/P2%20-%20Grafos/me%20de%20ibagens/Aula%2013%20-%20MST.png)

## Execução

# Kruskal's Algorithm (Minimum Spanning Tree)

![grafo_inicial_kruskal](/P2%20-%20Grafos/me%20de%20ibagens/Aula%2013%20-%20MST.png)

## Execução