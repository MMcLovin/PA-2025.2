# Algoritmo de Dijkstra

* Serve para encontrar o menor caminho
    * **Mas BFS já não fazia isso?**
    * Sim, porém, não levava em consideração o custo associado à travessia das arestas. Logo, o menor caminho nem sempre é o mais barato.

* d(u) = menor distância de um nó s até u
* `S = {s}, d(s) = 0`: Inicializamos S - o conjunto de nós já explorados - com s. Como s é o primeiro nó, o custo para chegarmos até ele foi zero.

* pi(v) = min[d(u) + ce]
* pi(c) = menor caminho
* ce = menor caminho para um próximo nó u não explorado

# Implementação Noob

![meh](/P2%20-%20Grafos/me%20de%20ibagens/Aula%2012%20-%20Dijkstra%20algo.png)

(já partimos do princípio que sabemos o nó que será a partida e o nó que será o destino)
1. Inicializa com o nó escolhido.
2. Pega os vizinhos dele e salva essas informações com os custos de ida.
    * Ao fazer isso, estamos olhando a "mancha" (que possui apenas s por enquanto) e as arestas que atravessam a borda da mancha e levam para outros nós.
3. Pegamos o vizinho cujo caminho tem o menor custo e salvamos essas informações com os custos de ida.
    * Podemos considerar que esse nó entrou na mancha aqui.
4. Analise o custo dos caminhos para os vizinhos desse vizinho de menor custo.
    * Nessa análise, nós olhamos se já não há um caminho de melhor custo para os vizinhos desse nó. Portanto, apenas salvaremos o caminho se ele for melhor que o caminho já explorado ou se ainda não há nenhum caminho explorado até aquele nó.
5. If !(nó de destino foi escolhido como a melhor opção ou foi o último nó a ser explorado): move to `2`.
6. Agora fazemos o backtracking para saber o caminho que levou do nó de origem até o nó de destino.

- Dicas:
    * Manter um conjunto dos nós já explorados.
    * Manter um conjunto das opções, para analisar se são melhores ou piores.

* **Complexidade** (O(n(n+m))) -> praticamente quadrática e, nos piores casos, pode ser cúbica.

// grafo direcionado, com os pesos nas arestas, totalmente explorado
![meh2](/P2%20-%20Grafos/me%20de%20ibagens/Aula%2012%20-%20Grafo%20explorado.png)

# Implementação refinada

* Vamos usar uma estrutura de dados mais robusta para armazenar as informações das nossas opções disponíveis ([MinHeap](https://www.youtube.com/watch?v=2DmK_H7IdTo)).

1. Inicializa o heap com o nó escolhido e seu custo incial como 0.
2. coloca os outros nós com custo infinito (∞)
3. For each v in G

    4. vizinhos = vizinhos(ExtractMin())
    5. marca o nó extraído como explorado
    6. For each v in vizinhos(s)

        6.1. Atualiza o custo do vizinho mais barato 

        6.2. Heapify() 

![yeah](/P2%20-%20Grafos/me%20de%20ibagens/Aula%2012%20-%20tabela%20de%20complexidades.png)

* **Complexidade** O(mlog(n))

* Dijkstra não funciona com arestas de peso negativo.
    * Como resolver isso? -> Bellman-Ford

* **Putz, na videoaula ele não chegou a fazer a execução usando MinHeap, mas na aula presencial ele fez...**
