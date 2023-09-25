# Vectores
Paso previo para el bloque de temas que inicia con POO (OOP en español).

- [ ] Ver "Tipo de clase"
- [ ] Ver Size y Capacity en acción

## Definición

Es una plantilla y un contenedor del tipo de clase _vector_ que puede almacenar _cualquier tipo de datos_ y que se guarda en la memoria _heap_. Pero solo almacenará elementos del mismo tipo por el momento.

Es una estructura secuencial indexada. Se puede cambiar el tamaño en cualquier momento, también vacío.

Controla automática y eficientemente el redimensionamiento y gestión de memoria.

Cuentan con **métodos y operadores** que permiten las acciones _crear_, _leer_, _borrar_, _actualizar_ y _manipular_ el contenedor.

Es como un array optimizado.

## Construcción
```{C++}
#include <vector>

vector<tipo de dato> vec;
vector<int> vec1; // vector de enteros
vector<string> vec22; // vector de strings
```

`std::vector` es un **tipo de clase** definido en la librería estándar STL.

```
#include <vector>

vector<int> vec1; //un tipo de clase genérica
int arreglo[100] = {} //una colección de elementos del mismo tipo
```

![vec](.\imagenes\vector.png)

- `begin()` retorna el puntero del primer elemento
- `at(n)` retorna el puntero del elemento en `n`
- `end()` retorna el puntero del elemento final
- `size()` retorna la cantidad de elementos. Por ejemplo, si inicializamos el vector con capacidad para 78 pero reservamos 200, retorna 78.
- `capacity()` retorna la capacidad como número de elementos. Por ejemplo, si inicializamos el vector con capacidad para 78 pero reservamos 200, retorna 200.

## Operadores básicos

**CRUD**

### C - Create - Crear
```
void vector_paso_por_valor(vector<int> v){
    //crea un vector para la función

    v[0]=1;
    v.at(0)=1; //lo mismo
}

void vector_paso_por_referencia(vector<int> &v){
    //modificando el vector

    v[0]=1;
    v.at(0)=1;
}

void vector_paso_por_referencia_const(const vector<int> &v){
    //el vector se vuelve constante, no se puede alterar

    cout << v.at(0);
}

//

vector<int> v(100);

reserve()
size()


```

Llamar por referencia al vector implica copiarlo, ya que el vector no es un puntero, es una _clase_.