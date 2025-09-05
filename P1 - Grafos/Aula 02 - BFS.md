# Breadth First Search

* Existem 3 tipos/formas de BFS:
1. De um nó qualquer para visitar todos os seus vizinhos imediatos (1 aresta de distância)
    * não existe ordem/hierarquia de visita aos vizinhos
    * o resultado da ordem em que os nós são visitados é uma árvore
    * para fazer a travessia de um grafo, precisamos de outra estrutura de dados para nos ajudar a organizar a ordem/sequência que exploramos, evitando cair em um ciclo
    * BFS usa lista e fila

    for every vertex s of G nor explored yet:
        do Enqueue(S,s);
        mark vertex s as visted
        while S is not empty do
        u = Dequeue(S);
        For each c in Adj[u] then
            if v is unexplored then
                mark edge (v,u) as tree edge
                mark vertex v as visited
                Enqueue(S,v)

    * A fila garante a exploração em camadas
    * A lista aqui é usada para representar os vizinhos dos nós
    * como faz análise de complexidade -> achar coisas discretas. Nesse caso, pode ser quantos nós entram na fila, são visitados
    * **ideia de exercício:** a partir de um grafo, escolher um nó de partida e montar a árvore resultante da BFS daquele grafo
    * essa abordagem, usando lista de adjacência para representação dos vizinhos, resulta em uma complexidade O(n+m); se fosse uma matriz de adjacência, seria O(n²)
2. De um
3. 
