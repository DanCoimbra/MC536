# Aluno
* 155077: Daniel Credico de Coimbra

## Tarefa de Cypher sobre Marcadores e Taxonomia

### Tarefa 1
```
MATCH (x :Marcador) -[:Pertence]-> (:Categoria {id:"Serviços"})
RETURN x
```

### Tarefa 2
```
MATCH (x1 :Marcador) -[:Pertence]-> (:Categoria {id:"Serviços"})
MATCH (x2 :Marcador) -[:Pertence]-> (:Categoria) -[:Superior]-> (:Categoria {id:"Serviços"})
MATCH (x3 :Marcador) -[:Pertence]-> (:Categoria) -[:Superior]-> (:Categoria) -[:Superior]-> (:Categoria {id:"Serviços"})
RETURN collect(x1) + collect(x2) + collect(x3)
```