Python oferece diversas estruturas de dados para armazenar, organizar e manipular informações de maneira eficiente
Essas estruturas podem ser classificadas em categorias básicas e avançadas

## 1. **Estruturas de Dados Básicas**

### **Listas (`list`)**
- Estrutura ordenada e mutável
- Permite elementos duplicados e diferentes tipos de dados
- Suporta operações como adição, remoção, ordenação e fatiamento


### **Tuplas (`tuple`)**
- Estrutura ordenada e imutável
- Armazena conjuntos fixos de dados


### **Conjuntos (`set`)**
- Estrutura não ordenada e mutável
- Não permite elementos duplicados
- Exemplo:
  ```python
  conjunto = {1, 2, 2, 3}
  print(conjunto)  # {1, 2, 3}
  ```

### **Dicionários (`dict`)**
- Mapeia pares de chave-valor
- Permite acesso rápido aos valores pelas chaves
- Exemplo:
  ```python
  dicionario = {"nome": "Ana", "idade": 25}
  print(dicionario["nome"])  # Ana
  ```

---

## 2. **Estruturas de Dados Avançadas**

### **Deque (`collections.deque`)**
- Lista otimizada para inserções e remoções rápidas nas extremidades
- Exemplo:
  ```python
  from collections import deque
  fila = deque([1, 2, 3])
  fila.appendleft(0)  # Adiciona no início
  print(fila)  # deque([0, 1, 2, 3])
  ```

### **Fila (`queue.Queue`)**
- Segue o princípio FIFO (First In, First Out)
- Exemplo:
  ```python
  from queue import Queue
  fila = Queue()
  fila.put("A")
  fila.put("B")
  print(fila.get())  # A
  ```

### **Pilha (Stack)**
- Segue o princípio LIFO (Last In, First Out)
  - Comportamento padrão das Listas
- Exemplo:
  ```python
  pilha = []
  pilha.append("A")
  pilha.append("B")
  print(pilha.pop())  # B
  ```

### **Heap (`heapq`)**
- Implementa uma fila de prioridade
- Exemplo:
  ```python
  import heapq
  numeros = [3, 1, 4]
  heapq.heapify(numeros)
  print(heapq.heappop(numeros))  # 1 (menor elemento)
  ```

### **Árvores e Grafos**
- Estruturas hierárquicas para organizar dados de forma eficiente
- Utilizadas em bancos de dados, redes e inteligência artificial
