Ejercicio de Gestión de Préstamos de Libros en una Biblioteca
Implementación en Python para gestionar los préstamos de libros en una biblioteca con ciertas actualizaciones y restricciones de acuerdoa libros prestados y demás.

Explicación:
Diccionario de libros: Se define un diccionario con cinco libros, cada uno identificado por un código alfanumérico, y con detalles del título, autor y año.

Conjunto de libros prestados: Se usa un conjunto (set) para llevar la cuenta de los libros que han sido prestados, ya que permite manejar elementos únicos y operaciones rápidas de búsqueda y eliminación.

Función para prestar libros: La función prestar_libro verifica si el libro está disponible antes de agregarlo al conjunto de libros prestados. Si ya está prestado o no existe, muestra un mensaje adecuado.

Función para devolver libros: devolver_libro verifica si el libro está prestado antes de permitir su devolución.

Mostrar libros disponibles: La función mostrar_libros_disponibles recorre el diccionario de libros y muestra aquellos que no han sido prestados.

Actualizar detalles de libros existentes: actualizar_detalles_libro permite modificar el título, autor o año de un libro específico, verificando que el código del libro exista antes de realizar los cambios.

Desafío adicional:
Intentar prestar libros inexistentes: Se verifica si el código del libro existe en el diccionario antes de proceder con el préstamo.
Actualizar detalles de libros existentes: Se añadió una función que permite actualizar los detalles del libro si existe.
Con este código puedes gestionar eficientemente el préstamo y devolución de libros en la biblioteca.

# Diccionario de libros disponibles
libros = {
    "B001": {"título": "The Great Gatsby", "autor": "F. Scott Fitzgerald", "año": 1925},
    "B002": {"título": "1984", "autor": "George Orwell", "año": 1949},
    "B003": {"título": "To Kill a Mockingbird", "autor": "Harper Lee", "año": 1960},
    "B004": {"título": "Moby Dick", "autor": "Herman Melville", "año": 1851},
    "B005": {"título": "Pride and Prejudice", "autor": "Jane Austen", "año": 1813}
}

# Conjunto de libros prestados
libros_prestados = set()

# Función para prestar un libro
def prestar_libro(codigo_libro):
    if codigo_libro in libros:
        if codigo_libro not in libros_prestados:
            libros_prestados.add(codigo_libro)
            print(f"El libro '{libros[codigo_libro]['título']}' ha sido prestado.")
        else:
            print(f"El libro '{libros[codigo_libro]['título']}' ya está prestado.")
    else:
        print(f"El libro con código {codigo_libro} no existe en la biblioteca.")

# Función para devolver un libro
def devolver_libro(codigo_libro):
    if codigo_libro in libros_prestados:
        libros_prestados.remove(codigo_libro)
        print(f"El libro '{libros[codigo_libro]['título']}' ha sido devuelto.")
    else:
        print(f"El libro con código {codigo_libro} no está prestado o no existe.")

# Función para mostrar los libros disponibles para préstamo
def mostrar_libros_disponibles():
    print("Libros disponibles para préstamo:")
    for codigo_libro, datos in libros.items():
        if codigo_libro not in libros_prestados:
            print(f"Código: {codigo_libro} | Título: {datos['título']} | Autor: {datos['autor']} | Año: {datos['año']}")

# Función para actualizar detalles de un libro existente
def actualizar_detalles_libro(codigo_libro, nuevo_titulo=None, nuevo_autor=None, nuevo_año=None):
    if codigo_libro in libros:
        if nuevo_titulo:
            libros[codigo_libro]["título"] = nuevo_titulo
        if nuevo_autor:
            libros[codigo_libro]["autor"] = nuevo_autor
        if nuevo_año:
            libros[codigo_libro]["año"] = nuevo_año
        print(f"Detalles del libro {codigo_libro} actualizados.")
    else:
        print(f"El libro con código {codigo_libro} no existe en la biblioteca.")

# Pruebas de las funciones

# Mostrar libros disponibles inicialmente
mostrar_libros_disponibles()

# Prestar un libro
prestar_libro("B003")

# Intentar prestar el mismo libro de nuevo
prestar_libro("B003")

# Intentar prestar un libro inexistente
prestar_libro("B999")

# Devolver un libro prestado
devolver_libro("B003")

# Intentar devolver un libro que no está prestado
devolver_libro("B003")

# Mostrar libros disponibles después de prestar/devolver
print("\nLibros disponibles después de préstamos:")
mostrar_libros_disponibles()

# Actualizar detalles de un libro existente
actualizar_detalles_libro("B001", nuevo_titulo="El Gran Gatsby", nuevo_autor="F. Scott Fitzgerald", nuevo_año=1926)

# Mostrar libros disponibles después de la actualización
print("\nLibros disponibles después de la actualización:")
mostrar_libros_disponibles()



![image](https://github.com/user-attachments/assets/e83f97a5-d577-4540-8b17-23df5b67bdfa)

![image](https://github.com/user-attachments/assets/a97edd87-09e5-4063-be61-c11855fd1423)

