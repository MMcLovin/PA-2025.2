# Grafos
* grafo = estrutura de dados mais livre que existe
* V = vértices (nós)
* E = edges (arestas)
* **grau de um nó** = número de vizinhos que ele tem, basicamente as arestas conectadas ao nó
* A soma dos graus de todos os nós é igual a 2 * E. Fica simples entender o 2 * E, pois a aresta é contada tanto quando "sai" de um nó quanto quando "chega"
* Então tudo é um grafo? Sempre foi
* grafo pode ser direcionado ou não direcionado

## Representações

#### Matriz de Adjacência (é uma matriz simétrica)
* a tabela que representa a relação entre os nós é do tamanho n²
* armazena as arestas que existem e também aquelas que não existem (maior desvantagem dessa representação)

|     |  V1 |  V2 |  V3 |  V4 |  V5 |
| :-: | :-: | :-: | :-: | :-: | :-: |
| V1  |  0  |  1  |  0  |  0  |  0  | 
| V2  |  1  |  0  |  1  |  0  |  0  |
| V3  |  0  |  1  |  0  |  1  |  1  |
| V4  |  0  |  0  |  1  |  0  |  0  |
| V5  |  0  |  0  |  1  |  0  |  0  |

V1 --------- V2
             |
             |
             |
             |
V4 --------- V3  --------- V5

#### Lista de Adjacência
* vantagem = armazena apenas as arestas que existem
* é uma lista em que cada item é uma lista encadeada com as relações de um nó
* porém usa mais memória, por causa do overhead da lista

## Caminho
* sequência de nós unidos por arestas
* caminho simples = nós não se repetem ao percorrer o caminho

## Ciclo
* o nó de partida é igual ao nó de chegada, sendo todos os nós intermediários distintos
* ciclo é o que diferencia e torna grafos mais complexos do que outras estruturas 

## Distância
* é igual ao menor caminho entre 2 vértices

# Árvores
* Um grafo não direcionado é uma árvore se ele é conectado (não há nós soltos) e não contém um ciclo
