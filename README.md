# Unidad 2: Componentes y librerías


## Unidad 2: Componentes y Librerías

### 2.1 Definición conceptual de componentes, paquetes / librerías

Los **componentes** son piezas de software reutilizables que encapsulan una funcionalidad específica. Pueden ser **visuales** (como botones, formularios, tablas) o **no visuales** (como funciones, clases o servicios).

Las **librerías o paquetes** son conjuntos organizados de componentes, funciones o clases que permiten reutilizar código y facilitar el desarrollo. Su objetivo principal es evitar que el programador tenga que crear todo desde cero.

En resumen:

* **Componente** → unidad individual reutilizable
* **Librería/paquete** → conjunto de componentes organizados

---

### **2.2 Uso de librerías proporcionadas por el lenguaje**

La mayoría de los lenguajes de programación incluyen librerías estándar que permiten realizar tareas comunes como:

* Manejo de archivos
* Operaciones matemáticas
* Manipulación de cadenas
* Conexión a bases de datos

Ejemplos:

* En Python: `math`, `datetime`, `os`
* En Java: `java.util`, `java.io`
* En JavaScript: librerías integradas del navegador o de Node.js

El uso de estas librerías permite:

* Ahorrar tiempo de desarrollo
* Reducir errores
* Mejorar la eficiencia del código

---

### **2.3 Creación de componentes (visuales y no visuales) definidos por el usuario**

Los programadores también pueden crear sus propios componentes para reutilizarlos en diferentes partes de un proyecto.

**Componentes visuales:**

* Botones personalizados
* Formularios
* Interfaces gráficas

**Componentes no visuales:**

* Funciones
* Clases
* Módulos

Ventajas:

* Reutilización de código
* Organización del proyecto
* Facilita el mantenimiento

Ejemplo conceptual:
Un desarrollador puede crear un componente llamado `Calculadora` que contenga métodos para sumar, restar, multiplicar y dividir.

---

### **2.4 Creación y uso de paquetes/librerías definidas por el usuario**

Un paquete o librería propia se crea agrupando varios componentes relacionados en una estructura organizada.

Pasos generales:

1. Crear los componentes (funciones o clases)
2. Organizarlos en archivos o módulos
3. Definir una estructura de carpetas
4. Importarlos en otros proyectos

Ejemplo:

* Crear un paquete llamado `utilidades`
* Incluir funciones como validación de datos, cálculos, etc.
* Reutilizar ese paquete en diferentes programas

Beneficios:

* Facilita la reutilización en múltiples proyectos
* Permite compartir código con otros desarrolladores
* Mejora la escalabilidad del software


