# Prueba de Programación Orientada a Objetos

## Mantenedor de Productos en Memoria

### Contexto

Una tienda necesita desarrollar una aplicación que permita registrar productos y posteriormente mostrar la información de los productos creados.

La información debe mantenerse únicamente durante la ejecución del programa. No se utilizarán bases de datos ni archivos.

El sistema deberá organizarse aplicando principios de Programación Orientada a Objetos y separando adecuadamente las responsabilidades.

## Requerimientos

### 1. Modelo general de artículos

Todos los artículos de la tienda comparten información común:

* Identificador.
* Nombre.
* Precio.

Se debe crear una estructura general que represente esta información y que pueda ser utilizada como base para definir tipos de artículos más específicos.

Además, todo artículo debe tener la capacidad de entregar una descripción de sí mismo.

### 2. Productos

El sistema debe manejar productos que compartan las características generales de un artículo.

Cada producto deberá contener adicionalmente:

* Stock disponible.
* Categoría.

Los productos deberán poder entregar una descripción propia, diferente a la descripción general definida para un artículo.

La información propia de un producto deberá representarse mediante una estructura orientada principalmente al almacenamiento de datos.

### 3. Categorías

Cada producto deberá pertenecer a una categoría.

El sistema considerará solamente las siguientes posibilidades:

* Tecnología.
* Hogar.
* Alimentos.

Cada categoría deberá permitir obtener una descripción que pueda mostrarse posteriormente en consola.

La solución debe impedir que se creen categorías distintas a las contempladas por el sistema.

### 4. Mantenedor en memoria

Se deberá crear un componente responsable de administrar los productos durante la ejecución del programa.

Los productos creados deberán almacenarse internamente en una colección.

La colección no deberá ser modificada directamente desde el programa principal.

El mantenedor deberá entregar únicamente las siguientes operaciones:

* Registrar un producto.
* Obtener los productos registrados.

### 5. Registro de productos

Al registrar un producto se deberán considerar las siguientes validaciones:

* El identificador debe ser mayor que cero.
* El nombre no puede estar vacío.
* El precio debe ser mayor que cero.
* El stock no puede ser negativo.
* No pueden existir dos productos con el mismo identificador.

La operación deberá permitir distinguir claramente cuándo el registro fue realizado correctamente y cuándo ocurrió un problema.

Cuando ocurra un problema se deberá entregar información que permita identificar la causa del error.

### 6. Cálculo de inventario

Para cada producto se deberá calcular el valor correspondiente al stock disponible.

El cálculo corresponde a:

**precio del producto × cantidad disponible**

Por ejemplo:

```text
Nombre: Teclado
Precio: 20.000
Stock: 5
Valor disponible: 100.000
```

Además, el programa deberá calcular el valor total correspondiente a todos los productos registrados.

### 7. Consulta de los productos

Utilizando la colección de productos registrados, el programa deberá realizar al menos una consulta o transformación adicional.

Por ejemplo:

* Obtener solamente los productos que tengan stock disponible.
* Obtener los productos pertenecientes a una determinada categoría.
* Obtener solamente los nombres de los productos registrados.
* Calcular el valor total del inventario.

Esta operación deberá realizarse utilizando las capacidades que Kotlin entrega para trabajar directamente con colecciones, evitando resolver toda la consulta mediante ciclos tradicionales.

### 8. Visualización

Los productos registrados deberán ser obtenidos desde el mantenedor y posteriormente recorridos para mostrar su información en consola.

Por cada producto se deberá mostrar como mínimo:

* Identificador.
* Nombre.
* Precio.
* Stock.
* Categoría.
* Valor correspondiente al stock disponible.
* Descripción del producto.

La salida deberá ser clara y ordenada.

### 9. Herencia y comportamiento

El programa deberá demostrar que un producto puede ser tratado como un artículo general.

A pesar de ser tratado mediante el tipo general, al solicitar su descripción deberá ejecutarse el comportamiento particular definido para el producto.

Esta situación deberá demostrarse durante la ejecución del programa.

### 10. Manejo de errores

El programa deberá controlar situaciones que puedan generar errores durante su ejecución.

Ante un error controlado, la aplicación deberá informar lo ocurrido y continuar ejecutándose cuando sea posible.

El registro de productos deberá contemplar tanto casos exitosos como casos fallidos.

### 11. Operación asíncrona

El programa deberá incluir una operación que simule un proceso que demora en completarse.

Por ejemplo, antes de mostrar los productos se puede simular una carga de información que tarde aproximadamente un segundo.

Esta operación deberá ejecutarse correctamente desde el programa principal antes de continuar con el resto del flujo.

### 12. Programa principal

El programa deberá demostrar como mínimo las siguientes situaciones:

1. Simular la carga inicial de información.
2. Registrar al menos tres productos válidos.
3. Intentar registrar al menos un producto que no cumpla las validaciones.
4. Mostrar claramente los resultados exitosos y fallidos del registro.
5. Controlar al menos una situación que pueda producir un error.
6. Obtener los productos registrados desde el mantenedor.
7. Recorrer y mostrar los productos.
8. Calcular el valor disponible de cada producto.
9. Calcular el valor total del inventario.
10. Realizar al menos una consulta o transformación sobre la colección.
11. Demostrar el comportamiento específico de un producto cuando es tratado como un artículo general.

## Consideraciones

* Utilizar tipos de datos adecuados para cada información.
* Diferenciar correctamente entre información que puede cambiar y aquella que no debería modificarse.
* Separar la lógica en funciones con responsabilidades claras.
* Utilizar una colección para mantener los productos durante la ejecución.
* Aplicar una jerarquía de clases.
* Representar los productos mediante una estructura orientada al almacenamiento de datos.
* Limitar las categorías únicamente a las definidas en el problema.
* Manejar adecuadamente los resultados exitosos y los errores.
* Implementar una operación asíncrona simple.
* No utilizar bases de datos ni archivos.
* No concentrar toda la lógica del programa en la función principal.
