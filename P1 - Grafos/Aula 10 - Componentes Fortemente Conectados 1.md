# SCC 1 (Strongly Connected Components)

* Um grafo fracamente conectado pode ter, internamente, componentes fortemente conectados.

* **Fracamente conectados** -> existe um caminho de ida e um caminho diferente para a volta.
* **Fortemente conectados** -> para todos os nós, eles são mutuamente conectados.

* Só se aplica a grafos direcionados.

## Algoritmo para testar SCC
* O algoritmo que usamos para testar se um grafo é fortemente conectado não funciona mais aqui, pois queremos saber apenas se uma parte, ou seja, um componente do grafo é fortemente conectado.
* BFS não serve aqui.
* DFS >>>>> BFS (Nesse caso)
* É muito sobre achar o nó certo para poder aplicar a DFS.
* Usa um pouquinho de tudo: pegamos um grafo e substituímos seus componentes conectados pela representação de um único nó.
* O problema que esse algoritmo busca resolver é como achar um componente em que a DFS não vaza para outros componentes.
* Quando substituímos um componente por um nó e isso faz com que, ao começar a DFS por esse nó, não haja outro lugar para ir, temos um sink node.
* `sink node`
* `source node`

### DFS Numbering
* pre(v) = tempo de visita na ida
* post(v) = tempo de visita na volta
* O primeiro nó visitado no componente C é chamado de c.
* O primeiro nó visitado no componente D é chamado de d.
* post(c) > post(d)

* "O maior post está em um componente source node. Na própria DFS Numbering, o maior post sempre está em um nó que está no source node.
