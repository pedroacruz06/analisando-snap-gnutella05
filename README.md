# Analisando Grafos do SNAP — p2p-Gnutella05

**Disciplina:** MATA53 Teoria dos Grafos — Universidade Federal da Bahia (UFBA)  
**Aluno:** Pedro Antonio Cruz  
**Professor:** Bruno Pereira dos Santos  
**Grafo atribuído:** G56 — `p2p-Gnutella05`  
**Fonte:** [Stanford SNAP](https://snap.stanford.edu/data/p2p-Gnutella05.html)

---

## Sobre o Projeto

Análise topológica e empírica de uma rede P2P real (Gnutella, agosto de 2002),
contendo **8.846 nós** e **31.839 arestas**. O trabalho cobre:

- Extração de métricas estruturais (grau, densidade, diâmetro, clustering)
- Benchmark de 8 algoritmos clássicos com intervalos de confiança (IC 95%)
- Detecção de propriedade Small-World e Lei de Potência
- Teste de robustez: falha aleatória vs. ataque direcionado aos hubs

---

## Como Executar

### 1. Pré-requisitos

Python 3.9+ com as bibliotecas:

```bash
pip install networkx matplotlib numpy scipy
```

### 2. Dataset

Baixe o arquivo `p2p-Gnutella05.txt` diretamente do SNAP:

```
https://snap.stanford.edu/data/p2p-Gnutella05.txt.gz
```

Descompacte e coloque na **raiz do repositório**, no mesmo nível do notebook.

### 3. Executar o Notebook

```bash
jupyter lab trabalho_pratico.ipynb
```

Execute as células **em ordem**, pois cada seção depende das variáveis
definidas nas células anteriores.

---

## Algoritmos Implementados

| Algoritmo | Complexidade | Grafo usado |
|---|---|---|
| BFS | O(V+E) | Comp. Gigante (não-dir.) |
| DFS | O(V+E) | Comp. Gigante (não-dir.) |
| Verificação de Eulerianidade | O(V+E) | Comp. Gigante (não-dir.) |
| Dijkstra | O((V+E) log V) | Comp. Gigante (não-dir.) |
| Floyd-Warshall | O(V³) | Ego-network do hub (~50 nós) |
| Tarjan (SCC) | O(V+E) | Grafo original direcionado |
| Prim (MST) | O((V+E) log V) | Comp. Gigante (não-dir.) |
| Kruskal (MST) | O(E log E) | Comp. Gigante (não-dir.) |

---

## Outputs Gerados

Após executar o notebook, dois arquivos são salvos automaticamente em `outputs/`:

- `distribuicao_graus.png` — distribuição de graus em escala log-log
- `visualizacao_grafo.png` — ego-network do nó hub (nó 842)

---

## Relatório

O relatório final em PDF está em `relatorio/relatorio_final.pdf`,
formatado no template WebMedia'2026 via Overleaf.
