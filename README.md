# Visualizador de Grafos — DFS y BFS

Animación paso a paso de los algoritmos de búsqueda **DFS** (Profundidad) y **BFS** (Anchura) sobre un grafo, usando Python en Jupyter Notebook o Google Colab.

---

## ¿Qué hace?

Muestra visualmente cómo recorre un grafo cada algoritmo, nodo por nodo, con colores que indican el estado de cada nodo en tiempo real. Al lado del grafo aparece un historial con el orden de visita y una barra de progreso.

| Estado del nodo | Color |
|---|---|
| Sin visitar | Blanco |
| Visitado anteriormente | Gris |
| Nodo actual | 🔵 Azul (BFS) / 🔴 Rojo (DFS) |

---

## Requisitos
```bash
pip install networkx matplotlib
```

## ¿Cómo usarlo?

1. Abre **Google Colab** o **Jupyter Notebook**
2. Copia y pega el código
3. Ejecuta la celda
4. Espera 3 segundos y empieza la animación

Primero se anima el **BFS**, luego el **DFS**. Cada paso dura 1 segundo.

---

## El grafo
```
        0
       / \
      1   2
     / \ / \
    3  4 5  6
        \ /
         7
```

Conexiones: `0-1, 0-2, 1-3, 1-4, 2-5, 2-6, 4-7, 6-7`

---

## Diferencia entre BFS y DFS

**BFS — Búsqueda por niveles**
Recorre el grafo nivel por nivel, como expandir ondas en el agua.
```
Orden: 0 → 1 → 2 → 3 → 4 → 5 → 6 → 7
```

**DFS — Búsqueda en profundidad**
Recorre el grafo siguiendo un camino hasta el fondo antes de devolverse.
```
Orden: 0 → 1 → 3 → 4 → 7 → 6 → 2 → 5
```

---

## Estructura del código

| Función | ¿Qué hace? |
|---|---|
| `bfs(grafo, inicio)` | Calcula el recorrido BFS usando una cola |
| `dfs(grafo, inicio)` | Calcula el recorrido DFS usando una pila |
| `animar(visitados, aristas_arbol, algoritmo)` | Muestra la animación paso a paso |

---

## Vista previa

Cada frame de la animación tiene dos paneles:
```
┌─────────────────────┬──────────────┐
│                     │ orden visita │
│     Grafo           │   [0]        │
│     animado         │   [1] ←      │
│                     │   ░░░░░░░    │
└─────────────────────┴──────────────┘
```

- **Panel izquierdo** → grafo con nodos coloreados
- **Panel derecho** → historial de nodos visitados + barra de progreso

---

## Personalización

Para cambiar el grafo, edita estas líneas:
```python
# Cambia las conexiones
grafo.add_edges_from([(0,1),(0,2), ...])

# Cambia las posiciones visuales de los nodos
posiciones = {
    0:(0,3), 1:(-1,2), ...
}
```

Para cambiar la velocidad de la animación:
```python
time.sleep(1)  # cambia 1 por los segundos que quieras entre cada paso
```

Autor: Charly Jhoan Murillo Hernandez (12200263)
---

Link del colab: https://colab.research.google.com/drive/1ozQxsPYy7FcSNodNFwj1pz5xM16kdU0g?usp=sharing
