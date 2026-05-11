# Sliding Puzzle — Algoritmos de Busca em Inteligência Artificial

Projeto desenvolvido para estudo e comparação de algoritmos de busca aplicados ao problema do **8-puzzle**, abordando técnicas de busca não informada e busca informada.

---

## Objetivo

Este trabalho tem como objetivo implementar e comparar diferentes algoritmos de busca aplicados ao problema do 8-puzzle.

Foram analisados algoritmos de:

- Busca em Largura (BFS)
- Busca em Profundidade (DFS)
- Busca em Profundidade Limitada (DLS)
- Busca em Aprofundamento Iterativo (IDS)
- Algoritmo A* (A-Star)

A avaliação considera:

- Tempo de execução
- Quantidade de nós explorados
- Qualidade da solução encontrada
- Uso de memória

---

## O Problema do 8-Puzzle

O 8-puzzle é um quebra-cabeças deslizante composto por:

- 8 peças numeradas
- 1 espaço vazio
- Tabuleiro 3x3

O objetivo é reorganizar as peças até atingir o estado final desejado.

### Estado Objetivo

```text
1 2 3
4 5 6
7 8 _
```

---

## Estado Inicial Utilizado

Nem todo estado inicial do 8-puzzle possui solução.

Isso ocorre devido à propriedade matemática da **paridade das inversões**.

Uma inversão acontece quando um número maior aparece antes de um número menor na sequência do tabuleiro (ignorando o espaço vazio).

Para o tabuleiro 3x3:

- número de inversões **par** → estado solucionável
- número de inversões **ímpar** → estado impossível

Por isso, o projeto utiliza apenas estados válidos.

### Exemplo de estado inicial

```python
tabuleiro = (1, 2, 3, 5, 0, 6, 4, 7, 8)
```

Representação visual:

```text
1 2 3
5 _ 6
4 7 8
```

---

## Algoritmos Implementados

### Busca em Largura (BFS)

- Garante a solução ótima
- Alto consumo de memória
- Explora os nós por níveis

Arquivo:

```text
1_buscaemlargurabfs.py
```

---

### Busca em Profundidade (DFS)

- Baixo consumo de memória
- Pode entrar em caminhos muito profundos
- Não garante a melhor solução

Arquivo:

```text
2_1busca_em_profundidadedfs.py
```

---

### Busca em Profundidade Limitada (DLS)

- Variante da DFS
- Define limite máximo de profundidade
- Evita expansões infinitas

Arquivo:

```text
2_2buscaemprofundidadelimitadadls.py
```

---

### Busca em Aprofundamento Iterativo (IDS)

- Combina vantagens de BFS e DFS
- Busca progressivamente mais profunda
- Garante solução ótima

Arquivo:

```text
2_3buscaemaprofundamentoiterativoids.py
```

---

### Algoritmo A* (A-Star)

- Busca informada
- Utiliza heurística para encontrar caminhos mais eficientes
- Melhor desempenho geral entre os algoritmos testados

Arquivo:

```text
3_1algoritmoastar.py
```

---

## Tecnologias Utilizadas

- Python 3
- Estruturas de dados:
  - fila
  - pilha
  - conjuntos
  - prioridade heap

---

## Como Executar

Clone o repositório:

```bash
git clone https://github.com/isalaberry/slidingpuzzle.git
```

Entre na pasta:

```bash
cd slidingpuzzle
```

Execute qualquer algoritmo:

```bash
python 1_buscaemlargurabfs.py
```

ou

```bash
python 3_1algoritmoastar.py
```

---

## Comparação Geral dos Algoritmos

| Algoritmo | Completo | Ótimo | Uso de Memória | Velocidade |
|---|---|---|---|---|
| BFS | Sim | Sim | Alto | Médio |
| DFS | Não | Não | Baixo | Alto |
| DLS | Parcial | Não | Baixo | Médio |
| IDS | Sim | Sim | Médio | Médio |
| A* | Sim | Sim | Baixo/Médio | Alto |

---

## Considerações Finais

O estudo do quebra-cabeças deslizante demonstrou, na prática, a importância de selecionar a técnica de Inteligência Artificial mais adequada conforme os recursos computacionais disponíveis e os requisitos do problema.

À medida que a complexidade cresce, o uso de buscas informadas torna-se essencial.

O algoritmo **A\***, aliado a uma função heurística adequada, mostrou-se a abordagem mais eficiente para conciliar:

- rapidez
- baixo custo de memória
- obtenção do melhor caminho possível
