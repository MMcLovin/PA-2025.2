# Bipartição

* Permite, em alguns casos, tornar situações solucionáveis
* Pode melhorar a complexidade
* Podemos redesenhar um grafo para biparti-lo
* Se um grafo possuir um ciclo de tamanho ímpar, ele não pode ser bipartido

## Checagem da bipartição
* Modificação da BFS

### Marcando a camada 
* Consiste em fazer modificações no enqueue para enfileirar também a camada do nó enfileirado
* Na hora de fazer o if para os nós da lista de adjacência Adj[v], podemos fazer um else que verifica/valida que há arestas entre nós da mesma camada, o que já prova que não é um grafo bipartido

### Usando cores
* No primeiro enfileirar da BFS a gente escolhe uma cor para enfileirar, daí na segunda vez enfileira o nó com opp_color(u)
* No else do if, se o vizinho for da mesma cor, já era 