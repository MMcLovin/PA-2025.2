# SCC 2 (Strongly Connected Components)

* Corolário: o nó em G com maior `Post(v)` fica em um ***source node***, que é um SCC (componente fortemente conectado).

* Os SCC permanecem os mesmos ao calcular o grafo reverso.

* Se um nó é o ***source node*** em G~, então no grafo reverso Grev ele é o ***sink node***.

* ***source node*** = nó que não tem arestas chegando nele, ou seja, apenas saem arestas dele.
* ***sink node*** = nó que não tem arestas saindo dele, ou seja, apenas chegam arestas nele.

* BFS -> tem a vantagem de fornecer o menor caminho.
* DFS (rodando 2 vezes, uma em G e outra em Grev) -> tem a vantagem de, com os Post(v), nos ajudar a achar o ***source node*** e o ***sink node***.

# Algoritmo de Kosaraju (forma final do algoritmo)
* **Objetivo:** encontrar todos os componentes fortemente conectados em um grafo direcionado
Dado um grafo G:
1. Rode a DFS até o final (anotando pré e post).
2. Selecione o v com o maior post(v).
3. Faça o Grev.
4. Identificou um SCC? Abstraia esse nó do Grev.
5. Ainda há nós? Olhe para o G resultante da DFS em 1 e pule para o `2.`.
6. That's all, folks.