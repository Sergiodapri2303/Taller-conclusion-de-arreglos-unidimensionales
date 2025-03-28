# Taller conclusión de arreglos unidimensionales
### Nicolas A. Vargas Angarita - Sergio Prieto Vargas
## Codigo python
``` python
vertices = []
caras = []

num_vertices = int(input("¿Cuántos vértices hay? "))

for i in range(num_vertices):
    x = float(input(f"Vértice {i+1} - X: "))
    y = float(input(f"Vértice {i+1} - Y: "))
    z = float(input(f"Vértice {i+1} - Z: "))
    vertices.append((x, y, z))

num_caras = int(input("¿Cuántas caras hay? "))

for i in range(num_caras):
    cara = list(map(int, input(f"Índices de la cara {i+1} (separados por espacio): ").split()))
    caras.append(cara)

print("\nVértices:")
for i, v in enumerate(vertices, 1):
    print(f"V{i}: {v}")

print("\nCaras:")
for i, c in enumerate(caras, 1):
    print(f"F{i}: {c}")
```
# Codigo C++
``` C++
#include <iostream>
using namespace std;

int main() {
    float vertices[100][3];
    int caras[100][10], total_vertices, total_caras, cantidad_vertices;

    cout << "Ingrese la cantidad de vértices: ";
    cin >> total_vertices;

    for (int i = 0; i < total_vertices; i++) {
        cout << "Vértice " << i+1 << ":\n";
        cout << "  Coordenada X: "; cin >> vertices[i][0];
        cout << "  Coordenada Y: "; cin >> vertices[i][1];
        cout << "  Coordenada Z: "; cin >> vertices[i][2];
    }

    cout << "Ingrese la cantidad de caras: ";
    cin >> total_caras;

    for (int i = 0; i < total_caras; i++) {
        cout << "Ingrese la cantidad de vértices para la cara " << i+1 << ": ";
        cin >> cantidad_vertices;
        cout << "Ingrese los índices de los vértices de la cara " << i+1 << " (separados por espacio): ";
        for (int j = 0; j < cantidad_vertices; j++) {
            cin >> caras[i][j];
        }
        caras[i][cantidad_vertices] = -1; // Marcador de fin
    }

    cout << "\nLista de Vértices:\n";
    for (int i = 0; i < total_vertices; i++) {
        cout << "V" << i+1 << ": (" << vertices[i][0] << ", " << vertices[i][1] << ", " << vertices[i][2] << ")\n";
    }

    cout << "\nLista de Caras:\n";
    for (int i = 0; i < total_caras; i++) {
        cout << "F" << i+1 << ": ";
        for (int j = 0; caras[i][j] != -1; j++) {
            cout << caras[i][j] << " ";
        }
        cout << "\n";
    }
    return 0;
}
```
Funcionamiento Paso a Paso c++

Declaración de Variables:

vertices[100][3]: Matriz para almacenar hasta 100 vértices con coordenadas (X, Y, Z).

caras[100][10]: Matriz para almacenar hasta 100 caras con un máximo de 10 vértices cada una.

total_vertices: Almacena el número de vértices ingresados.

total_caras: Almacena el número de caras ingresadas.

cantidad_vertices: Almacena el número de vértices de una cara específica.

Ingreso de Vértices:

Se solicita al usuario el número de vértices.

Se usa un bucle for para pedir las coordenadas (X, Y, Z) de cada vértice.

Los valores se almacenan en la matriz vertices.

Ingreso de Caras:

Se solicita el número de caras.

Para cada cara, se pregunta cuántos vértices la componen.

Se almacenan los índices de los vértices en la matriz caras.

Se utiliza -1 como marcador de fin de cada cara para delimitar los datos.

Impresión de Datos:

Se imprimen los vértices con su identificador (V1, V2, etc.).

Se imprimen las caras con los índices de los vértices que las componen.

Funcionamiento Paso a Paso (python)

Se inicializan dos listas vacías:

vertices: Para almacenar las coordenadas de los vértices.

caras: Para almacenar las caras, definidas por índices de los vértices.

Se solicita al usuario el número de vértices y se itera para capturar sus coordenadas:

Se usa input() para pedir el número de vértices.

En cada iteración, se solicitan las coordenadas x, y y z.

Se almacenan los valores en una tupla (x, y, z) dentro de vertices.

Se solicita al usuario el número de caras:

Se usa input() para pedir el número de caras.

En cada iteración, se solicita al usuario que ingrese los índices de los vértices que conforman la cara.

Se usa map(int, input().split()) para convertir los valores ingresados en una lista de enteros y almacenarlos en caras.

Finalmente, el código imprime la lista de vértices y caras en un formato legible:

Se usa enumerate() para mostrar los vértices con un identificador (V1, V2, etc.).

Se usa otro enumerate() para mostrar las caras con un identificador (F1, F2, etc.).


