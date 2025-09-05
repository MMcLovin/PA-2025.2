# Conectividade

## Grafos Direcionados
* Tudo o que vimos até agora foram grafos não direcionados
* Agora, as soluções de busca e travessias precisam ser revisitadas para validá-las
* BFS e DFS não são impactadas

* Temos um novo conceito -> conectividade forte
* **Fracamente conectados** -> existe um caminho de ida e um caminho diferente para a volta
* **Fortemente conectados** -> se para todos os nós, eles são mutuamente conectados

## Algoritmo Para Testar Conectividade Forte
* Como provar que um grafo é fortemente conectado -> precisamos apenas achar um nó em que todos os outros nós cheguem até ele e que, dele, você chegue até todos os outros nós -> **BFS**
* **Objetivo:** 
    * Escolha um nó aleatório s em G
    * Execute BFS no G
    * Execute BFS no Grev
    * Verdadeiro -> é fortemente conectado se a árvore gerada nas BFSs são iguais
    * Falso -> caso contrário
        - OBS: se ao rodar a BFS, não chegarmos a todos os nós, meio que já podemos parar pois não é fortemente conectado

* **Complexidade:** O(m+n)
* **Faz Parte do Segundo tipo de busca (Aula 04)**

## Grafo Reverso (Grev)
* Grev = pega um grafo e inverte o sentido de todas as arestas

### Algoritmo para reverter um grafo
* **Objetivo:** achar o Grev né porra
* Curiosidade, acho que ele é in-place, quem diria que esse conceito teria mais utilidade.
* Ideia de exercício -> pegar um grafo e fazer o reverso usando o vetor de lista de adjacência