# 📘 Unidad 2: Componentes y Librerías

## 📌 Descripción

Este repositorio contiene los ejemplos desarrollados durante la **Unidad 2: Componentes y Librerías**, donde se aplican conceptos fundamentales como el uso de librerías, creación de componentes reutilizables y estructuración de interfaces gráficas con Python utilizando Flet.

---

##  Contenido

###  2.1 Definición conceptual

Los **componentes** son bloques reutilizables que permiten construir interfaces y funcionalidades.
Las **librerías o paquetes** son conjuntos de código ya creado que facilitan el desarrollo.

En esta unidad se utilizaron:

* `flet` → Interfaces gráficas
* `matplotlib` → Gráficas
* `random` → Valores aleatorios

---

###  2.2 Uso de librerías

Ejemplo de uso de librerías externas para crear una aplicación interactiva.

####  Juego: Piedra, Papel o Tijera

```python
import flet as ft
import random

def main(page: ft.Page):
    page.title = "Juego: Piedra, Papel o Tijera"
    page.horizontal_alignment = ft.CrossAxisAlignment.CENTER
    page.vertical_alignment = ft.MainAxisAlignment.CENTER

    eleccion_usuario = {"valor": None}

    def seleccionar(opcion):
        eleccion_usuario["valor"] = opcion
        seleccion_texto.value = f"Elegiste: {opcion}"
        page.update()

    def jugar(e):
        if not eleccion_usuario["valor"]:
            resultado.value = ". Primero selecciona una opción"
            resultado.color = "red"
            page.update()
            return

        pc = random.choice(["Piedra", "Papel", "Tijera"])

        texto_usuario.value = f"Tú elegiste: {eleccion_usuario['valor']}"
        texto_pc.value = f"La PC eligió: {pc}"

        if eleccion_usuario["valor"] == pc:
            resultado.value = "¡Empate!"
            resultado.color = "blue"
        elif (
            (eleccion_usuario["valor"] == "Piedra" and pc == "Tijera") or
            (eleccion_usuario["valor"] == "Papel" and pc == "Piedra") or
            (eleccion_usuario["valor"] == "Tijera" and pc == "Papel")
        ):
            resultado.value = "¡Ganaste!"
            resultado.color = "green"
        else:
            resultado.value = "Perdiste"
            resultado.color = "red"

        page.update()

    titulo = ft.Text("Piedra, Papel o Tijera", size=30, weight="bold")

    botones_opciones = ft.Row(
        controls=[
            ft.ElevatedButton(" Piedra", on_click=lambda e: seleccionar("Piedra")),
            ft.ElevatedButton(" Papel", on_click=lambda e: seleccionar("Papel")),
            ft.ElevatedButton(" Tijera", on_click=lambda e: seleccionar("Tijera")),
        ],
        alignment=ft.MainAxisAlignment.CENTER
    )

    boton_jugar = ft.ElevatedButton("Jugar", on_click=jugar, width=200)

    seleccion_texto = ft.Text("")
    texto_usuario = ft.Text("")
    texto_pc = ft.Text("")
    resultado = ft.Text(size=20, weight="bold")

    page.add(
        titulo,
        ft.Divider(),
        botones_opciones,
        seleccion_texto,
        ft.Divider(),
        boton_jugar,
        ft.Divider(),
        texto_usuario,
        texto_pc,
        resultado
    )

ft.app(target=main)
```

---

###  2.3 Componentes definidos por el usuario

Creación de componentes reutilizables.

####  Tarjeta de perfil

```python
import flet as ft

class TarjetaPerfil(ft.Container):
    def __init__(self, nombre, rol, color_borde=ft.Colors.BLUE):
        super().__init__()
        self.content = ft.Column(
            controls=[
                ft.Text(nombre, weight=ft.FontWeight.BOLD, size=20),
                ft.Text(rol, italic=True),
                ft.ElevatedButton("Ver Perfil", on_click=self.saludar)
            ],
            tight=True
        )
        self.border = ft.border.all(2, color_borde)
        self.padding = 10
        self.border_radius = 10
        self.width = 200

    def saludar(self, e):
        print(f"Interactuando con {self.content.controls[0].value}")


def main(page: ft.Page):
    page.title = "Componentes"

    usuario1 = TarjetaPerfil("Ana Garcia", "Desarrolladora")
    usuario2 = TarjetaPerfil("Carlos Ruiz", "Arquitecto")

    page.add(usuario1, usuario2)

ft.app(target=main)
```

---

###  2.4 Uso de componentes reutilizables

Ejemplo tipo catálogo usando componentes personalizados.

```python
import flet as ft

productos = [
    {"nombre": "Laptop", "precio": 1200},
    {"nombre": "Mouse", "precio": 45}
]

class ProductoCard(ft.Container):
    def __init__(self, p):
        super().__init__()
        self.content = ft.Column([
            ft.Text(p["nombre"]),
            ft.Text(f"${p['precio']}")
        ])


def main(page: ft.Page):
    for p in productos:
        page.add(ProductoCard(p))

ft.app(target=main)
```

---

###  Ejemplo adicional: Dashboard con gráficas

Uso de múltiples librerías.

```python
import flet as ft
import matplotlib.pyplot as plt

# Código simplificado de gráficas
```

---

##  Cómo ejecutar

1. Instalar dependencias:

```bash
pip install flet matplotlib
```

2. Ejecutar archivo:

```bash
python nombre_archivo.py
```

---

##  Conclusión

El uso de componentes y librerías permite desarrollar aplicaciones más rápidas, organizadas y reutilizables. Además, facilita la creación de interfaces modernas y funcionales.
