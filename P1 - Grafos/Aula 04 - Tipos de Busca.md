# Tipos de busca

## BFS
* Para uma mesma abordagem de busca, podemos ter variações devido à forma como os parâmetros são passados para as buscas.
1. Passando só o grafo como parâmetro:
    - Gera a árvore até mesmo dos nós desconectados.
2. Passando o grafo e o nó inicial como parâmetro:
    - Irá gerar a árvore apenas dos nós com caminhos até o nó passado como parâmetro.
3. Passando o grafo, o nó inicial e o nó final como parâmetro:
    - Assim que encontrar/chegar no nó final, não processa mais nada, encerrando a execução.

* **A MESMA COISA SE APLICA À DFS**
