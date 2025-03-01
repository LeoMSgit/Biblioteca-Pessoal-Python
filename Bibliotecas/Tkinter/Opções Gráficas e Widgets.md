# Widgets e Funcionalidades do Tkinter

Este documento reúne as principais funcionalidades do Tkinter, incluindo widgets gráficos, gerenciadores de layout, controle de variáveis, estilização e eventos.

## 1. Widgets do Tkinter
Os widgets são os componentes gráficos usados para criar interfaces no Tkinter. Abaixo estão os principais:

### 1.1 Label
Exibe um texto ou imagem na interface.
```python
from tkinter import Tk, Label

root = Tk()
label = Label(root, text="Texto Exemplo")
label.pack()
root.mainloop()
```

### 1.2 Button
Cria um botão interativo.
```python
from tkinter import Tk, Button

def acao():
    print("Botão pressionado")

root = Tk()
botao = Button(root, text="Clique Aqui", command=acao)
botao.pack()
root.mainloop()
```

### 1.3 Entry
Campo de entrada de texto para o usuário.
```python
from tkinter import Tk, Entry

root = Tk()
entrada = Entry(root)
entrada.pack()
root.mainloop()
```

### 1.4 Frame
Contêiner para agrupar outros widgets.
```python
from tkinter import Tk, Frame, Label

root = Tk()
frame = Frame(root)
frame.pack()
label = Label(frame, text="Dentro do Frame")
label.pack()
root.mainloop()
```

### 1.5 Checkbutton
Botão de seleção com opção ativada/desativada.
```python
from tkinter import Tk, Checkbutton, IntVar

root = Tk()
var = IntVar()
check = Checkbutton(root, text="Opção", variable=var)
check.pack()
root.mainloop()
```

### 1.6 Radiobutton
Botão de seleção única dentro de um grupo.
```python
from tkinter import Tk, Radiobutton, IntVar

root = Tk()
var = IntVar()
radio1 = Radiobutton(root, text="Opção 1", variable=var, value=1)
radio2 = Radiobutton(root, text="Opção 2", variable=var, value=2)
radio1.pack()
radio2.pack()
root.mainloop()
```

### 1.7 Listbox
Lista de opções para o usuário.
```python
from tkinter import Tk, Listbox

root = Tk()
lista = Listbox(root)
lista.insert(1, "Opção 1")
lista.insert(2, "Opção 2")
lista.pack()
root.mainloop()
```

### 1.8 Progressbar
Indicador de progresso.
```python
from tkinter import Tk, ttk

root = Tk()
barra = ttk.Progressbar(root, length=200, mode='determinate')
barra.pack()
barra.start(10)
root.mainloop()
```

## 2. Gerenciadores de Layout
O Tkinter possui três métodos principais para organizar widgets na interface.

### 2.1 Pack
Organiza os elementos em blocos.
```python
widget.pack(side="top", fill="x")
```

### 2.2 Grid
Organiza os elementos em uma grade.
```python
widget.grid(row=0, column=1)
```

### 2.3 Place
Posicionamento absoluto com coordenadas.
```python
widget.place(x=50, y=100)
```

## 3. Controle de Variáveis
O Tkinter utiliza variáveis especiais para armazenar valores dinâmicos.

### 3.1 StringVar
Armazena e atualiza strings.
```python
from tkinter import Tk, StringVar, Entry

root = Tk()
var = StringVar()
entrada = Entry(root, textvariable=var)
entrada.pack()
var.set("Texto inicial")
root.mainloop()
```

### 3.2 IntVar
Armazena números inteiros.
```python
from tkinter import Tk, IntVar, Checkbutton

root = Tk()
var = IntVar()
check = Checkbutton(root, text="Opção", variable=var)
check.pack()
root.mainloop()
```

## 4. Estilização com ttk.Style
A biblioteca ttk permite personalizar a aparência dos widgets.

Os estilos disponíveis no Windows são: 'winnative', 'clam', 'alt', 'default', 'classic', 'vista', 'xpnative'

```python
from tkinter import Tk, ttk

root = Tk()
estilo = ttk.Style()
estilo.configure("TButton", font=("Arial", 12), padding=10)
botao = ttk.Button(root, text="Botão Estilizado", style="TButton")
botao.pack()
root.mainloop()
```

## 5. Eventos e Bindings
O Tkinter permite associar eventos aos widgets, como cliques ou pressionamento de teclas.

### 5.1 Bind para Clique do Mouse
```python
from tkinter import Tk, Label

def clique(event):
    print("Clicado!")

root = Tk()
label = Label(root, text="Clique aqui")
label.pack()
label.bind("<Button-1>", clique)
root.mainloop()
```

### 5.2 Bind para Tecla Pressionada
```python
from tkinter import Tk

def tecla_pressionada(event):
    print("Tecla pressionada:", event.keysym)

root = Tk()
root.bind("<KeyPress>", tecla_pressionada)
root.mainloop()
```

### 5.3 Uso de after para Execução Programada
```python
from tkinter import Tk, Label

def atualizar():
    label.config(text="Texto atualizado")

root = Tk()
label = Label(root, text="Texto original")
label.pack()
root.after(2000, atualizar)  # Atualiza após 2 segundos
root.mainloop()
```
