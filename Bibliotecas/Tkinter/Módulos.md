# 📌 Importação do Módulo Tkinter

```python
from tkinter import *
from tkinter import ttk
```

---

# Módulos Adicionais do Tkinter

## 1 tkinter (Módulo Principal)  
O núcleo do Tkinter, que permite criar **interfaces gráficas (GUI)** em Python.  

## 2 tkinter.ttk  
Alternativa mais moderna ao `tkinter`, oferecendo **widgets estilizados**.  

**Exemplo:**  

```python
from tkinter import Tk, ttk

root = Tk()
botao = ttk.Button(root, text="Clique Aqui")  # Botão estilizado
botao.pack()
root.mainloop()
```

---

## 3 tkinter.commondialog  
Classe base para os diálogos de outros módulos.

## 4 tkinter.colorchooser  
Exibe uma **caixa de diálogo para escolher cores**.  

**Exemplo:**  

```python
from tkinter import Tk, colorchooser

root = Tk()
root.withdraw()  # Esconde a janela principal

cor = colorchooser.askcolor(title="Escolha uma cor")
print("Cor escolhida:", cor)
```

---

## 5 tkinter.filedialog  
Permite abrir/selecionar arquivos.  

**Exemplo:**  

```python
from tkinter import Tk, filedialog

root = Tk()
root.withdraw()

arquivo = filedialog.askopenfilename(title="Escolha um arquivo")
print("Arquivo selecionado:", arquivo)
```

---

## 6 tkinter.font  
Permite **personalizar fontes** no Tkinter.  

**Exemplo:**  

```python
from tkinter import Tk, Label
import tkinter.font as tkFont

root = Tk()
fonte_personalizada = tkFont.Font(family="Arial", size=16, weight="bold")
label = Label(root, text="Texto com fonte customizada", font=fonte_personalizada)
label.pack()
root.mainloop()
```

---

## 7 tkinter.messagebox  
Exibe **mensagens de alerta** ou notificações.  

**Exemplo:**  

```python
from tkinter import Tk, messagebox

root = Tk()
root.withdraw()

messagebox.showinfo("Informação", "Isso é uma mensagem de alerta!")
```

---

## 8 tkinter.scrolledtext  
Adiciona uma **área de texto com rolagem automática**.  

---

## 9 tkinter.simpledialog  
Fornece **diálogos básicos para entrada de dados**.  

**Exemplo:**  

```python
from tkinter import Tk, simpledialog

root = Tk()
root.withdraw()

nome = simpledialog.askstring("Entrada", "Qual é o seu nome?")
print("Nome digitado:", nome)
```

---
