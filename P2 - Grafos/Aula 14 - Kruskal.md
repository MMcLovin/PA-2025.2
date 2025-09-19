# Kruskal (Minimum Spanning Tree)

* Aqui tem um bagulho muito importante = Union-Find 
* Faz parte da ideia de garantir que toda vez que a gente for adicionar uma aresta, a gente não crie um ciclo

* `Find(u)` = encontra em qual arvore o vértice `u` está. Ela faz isso em Log(n), pois vai percorrendo os pais até chegar na raiz
* `Union(u,v)` = une as árvores `u` e `v`
* "Mas poxa, ter que pagar O(log n) toda vez que eu for fazer um Find é meio caro, né?", sim, podemos pensar inicialmente que guardar em cada nó a raiz da árvore que ele pertence, certo?
* Nem tanto, pois assim, toda vez que fizermos um Union(u,v), vamos ter que atualizar todos os nó de uma das árvores para apontar para a raiz da outra árvore, o que é ~O(n)
* O que o gênio do Kruskal fez: transformou o Find(u) em quase O(1) com uma técnica chamada Path Compression e o Union by Rank.

## Estrutura do Union-Find

* A árvore gerada pelo union find NÃO é a MST
* Cada nó vira uma "árvore" independente ("Floresta de árvores"), que aponta para si mesmo
* Cada árvore tem um nível, que é a altura da árvore

1. supunhetamos que já temos um vetor ordenado de todas as arestas, do menor peso para o maior peso
3. fazemos Find(A) e Find(B)
4. If Find(A) != Find(B) -> não estão na mesma árvore -> Union(A,B) 
    * se Nível(A) > Nível(B) -> B aponta para A (Isso acontece para manter a árvore mais "achatada" possível, deixando o custo do Find menor)
    * se Nível(A) == Nível(B) -> Foda-se, escolhe um pra ser a raiz 
    * Atualiza o nível da árvore raiz (se necessário)
5. If Find(A) == Find(B) -> estão na mesma árvore -> não faz nada (Descarta a aresta)
6. Adiciona a aresta na MST
7. repete até ter n-1 arestas na MST

* O kruskal vai trabalhando com pedaços soltos de árvore, não segue a lógica de conectar cuts ou manchas que nem o Djikstra e Prim

* LEMBRANDO QUE A ORDEM QUE AS ARESTAS ENTRAM NA MST IMPORTA