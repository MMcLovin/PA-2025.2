# Prim (Minimum Spanning Tree)

* Grafo conectado, não direcionado e com pesos nas arestas
* MST = Árvore que contém todos os nós do grafo, mas de tal modo que a soma dos custos das arestas usadas seja o menor possível
* Vários algoritmos nos dão um MST:
    * Kruskal
    * Prim
    * Reverse-Delete

* Cut = subconjunto de nós.
* aresta de corte = aresta que conecta um nó do Cut a um nó fora do Cut.

# Prim's Algorithm

* Foi um desenvolvimento colaborativo, de Prim 1959, Dijkstra 1957 e Jarník 1930.

## The Algorithm Itself

![idea-of-it](/P2%20-%20Grafos/me%20de%20ibagens/Aula%2013%20-%20espirito%20da%20coisa.png)

### Naive Aproach
1. Escolhemos um nó inicial arbitrário.
2. Anotamos esse nó como parte do MST.
3. Anotamos todas as arestas de corte (as que conectam o nó escolhido a outros nós).
4. Escolhemos a aresta de corte de menor custo. (Se houver empate, escolha arbitrariamente uma delas)
5. Anotamos o nó conectado a essa aresta como parte do MST.
6. If !(todos os nós foram escolhidos): pass
7. Anotamos todas as arestas de corte (as que conectam os nós já escolhidos a outros nós).
8. Jump to `4.`.

* **Complexidade**: O(m*n) 

![final-mst](/P2%20-%20Grafos/me%20de%20ibagens/Aula%2013%20-%20final%20graph%20with%20naive%20aproach.png)

### Refined Aproach
* Usamos uma MinHeap para armazenar a aresta de menor custo que leva a um nó especifico, ou seja, guardamos a informação da aresta de menor custo para adicionarmos aquele nó ao Cut

![min-heap](/P2%20-%20Grafos/me%20de%20ibagens/Aula%2013%20-%20Prim%20with%20heap%20pseudocode.png)

1. Para cada vértice, dizemos que o custo para alcançá-lo é infinito (exceto para o nó inicial, cujo custo é 0)
2. Para cada vértice, vamos inserindo na MinHeap
3. Inicializamos o conjunto de nós explorados (Cut) como vazio
4. While !(MinHeap está vazia):
    1. Extraímos o nó da raiz da MinHeap (pode ser qualquer nó por enquanto, pois todos estão com custo infinito)
    2. Como é o nó inicial, o custo que tivemos para chegar nele é 0
    3. Adicionamos u ao Cut
    4. Para cada aresta que sai de u:
        1. Se o custo da aresta for menor que o custo armazenado para v na MinHeap && v ainda não está no Cut:
            1. Atualizamos o custo de v na MinHeap para o custo da aresta (u, v)
            2. Atualizamos a aresta que leva a v para ser (u, v)

* Ao usar uma heap, armazeamos apenas n nós, ao invés de m arestas e normalmente m >> n.

* OBS: coisas que armazenamos na MinHeap:
    * nó
    * custo para chegar nele
    * aresta que leva a ele

Onde que tá o heapify nessa bagaça?
* Sempre que atualizamos o custo de um nó na MinHeap, fazemos o heapify para cima (sift-up).

* **Complexidade**: O(m*log(n))

* É um algoritmo bem parecido com Dijkstra.
    * A diferença é que Dijkstra tenta minimizar o custo do caminho de um nó s até um nó t, enquanto Prim tenta minimizar o custo total do caminho que passa por todos os nós.