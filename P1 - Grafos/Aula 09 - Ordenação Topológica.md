# Grafos Direcionados Acíclicos (DAGs)

* Se o grafo tem ordenação topológica, ele é um DAG.
* Mas se ele é um DAG, ele tem ordenação topológica? Sim.
* É um DAG se podemos montar uma estrutura linear em que as arestas se movem somente em um sentido, o que o torna acíclico.
* Todo DAG possui um nó em que não chegam arestas, ou seja, apenas saem dele.

## Encontrando o nó inicial (com grau de entrada zero)

* Para saber para quem um nó aponta, é só olhar para a lista de adjacência dele.
* Mas e para saber quem aponta para ele? → Se o nó não tem arestas chegando nele, apenas saindo, se fizermos o grafo reverso, esse nó não aponta para ninguém, ou seja, a lista de adjacência dele estará vazia. Esse é um modo, porém, há outro mais fácil.

![P1 - Grafos/ibagens/aula 9 - achando no sem seta que chega.png](/P1%20-%20Grafos/me%20de%20ibagens/Aula%2009%20-%20achando%20no%20sem%20seta%20que%20chega%20(Ord%20Topológica).png)

### Abordagem com Heap (Complexidade O(log n (m+n)))

    1. Faça uma lista que, ao invés de ser uma lista de adjacência, é um contador para cada nó com quantas arestas chegam nele.
    2. Ache o nó com o menor contador.
    3. Exclua ele.
    4. Atualize o contador dos vizinhos.
    5. Se ainda existem nós, volte para o passo `2`.
    6. Acabou :)
* Complexidade = O(logn(m+n))

### Algoritmo Otimizando
* **Objetivo:** realizar uma ordenação topológica de um Grafo Direcionado Acíclico (DAG) de forma eficiente

    * Também temos um vetor com o contador para cada nó.
    * Porém, também uma outra ED auxiliar chamada candidatos, que armazena apenas os nós com contador igual a zero.
    * Ao invés de varrer o vetor procurando o contador de menor valor, nós sempre apenas pegamos o primeiro candidato da nossa ED auxiliar, excluímos ele, atualizamos os vizinhos e, se alguém é atualizado para 0, mandamos ele para candidatos.
* Complexidade = O(m+n)