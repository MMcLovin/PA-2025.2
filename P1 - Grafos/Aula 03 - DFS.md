# Depth First Search

* abordagem recursiva
* Não retorna o menor caminho (vou supor que a BFS retorna)
* Chamadas recursivas podem estourar a stack call quando o número de nós for grande o suficiente
* Porém, podemos usar uma pilha para substituir a recursividade
* Geralmente a BFS é mais útil
* Possuem complexidade igual

DFS(G)
    Para todo v em G
        Se v não visitado então
            DFS-Visit(G,v)

DFS-Visit(G,v)
    Marque v como visitado
    Para todo w em Adv(v)
        Se w não visitado então
            Insira aresta (v,w) na árvore
            DFS-Visit(G,w)

## Propriedades

## Dúvidas
* Não compreendi nenhuma das duas propriedades
* O que diabos é um ancestral?
