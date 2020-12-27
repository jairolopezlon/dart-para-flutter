# Sintaxis de Dart

-   [Tipado dinamico](#tipado_dinamico)

📍 _los ejemplos de codigo funcional se alojaran en este [link codigo](https://repl.it/repls/folder/introduccion-dart) los ejemplos se tendran en repl.it y medio de las guias se podra encontrar link a ejemplos funcionales_

-   Nota: para ejecutar el codigo de dart es necesario que este siempre se encuentre dentro de la funcion `main`.

como ejemplo de esto, nuestro primer "hola mundo" en dart, quedaria asi:

```dart
void main(){
    print("hola mundo!"); //hola mundo!
}
```

En dart, todas las sentencias terminan en punto y coma ";", excetuando las clases, metodos, funciones, condicional if, ciclo for.

## Tipado

Dart puede ser de tipado fuerte, debil o dinamico, pero por buena practica es recomendable mantenerlo con tipado fuerte.

### Tipado debil

podemos hacer uso de la palabra reservada `var`, la cual nos sirve para declarar una variable que tendra tipado debil, ej:

```dart
var nameVar;
nameVar = 32;
```

con la declaracion por medio de `var` sucede algo curioso a tener en cuenta; si al momento de de usar `var`solo declaramos la variable y no asignamos ningun valor, esta permitira realizar reasignacion dinamica, es decir podemos reasignarle un valor de tipo diferente y no presentara error.

pero se presenta una situacion diferente cuando se usa `var` para declarar y asignar valor inicial, en este caso la variable tomara el tipo del primer valor que se asigne, y no permitira tener tipado dinamico.

-   [Replit - tipado debil con error](https://repl.it/@JairoLopez2/tipado-debil-error#main.dart)

```dart
void main() {
    var nameVar = 45;
    print('${nameVar} es tipo ${nameVar.runtimeType}');
    nameVar = 45.6;
    print('${nameVar} es tipo ${nameVar.runtimeType}');
    nameVar = "jairo";
    print('${nameVar} es tipo ${nameVar.runtimeType}');
    nameVar = true;
    print('${nameVar} es tipo ${nameVar.runtimeType}');
}
```

-   [Replit - tipado debil sin error](https://repl.it/@JairoLopez2/tipado-debil)

```dart
void main() {
    var nameVar;
    nameVar = 45;
    print('${nameVar} es tipo ${nameVar.runtimeType}');
    nameVar = 45.6;
    print('${nameVar} es tipo ${nameVar.runtimeType}');
    nameVar = "jairo";
    print('${nameVar} es tipo ${nameVar.runtimeType}');
    nameVar = true;
    print('${nameVar} es tipo ${nameVar.runtimeType}');
}
```

<a name="tipado_dinamico"></a>

### Tipado dinamico

las varibles con tipado dinamico, pueden ser asignadas y reasignadas con cualqier tipo de valor; con el tipado dinamico se puede solucionar el error presentado en el tipado debil, si en el mismo caso del tipado debil, en vez usar la palabra `var` se usar la palabra `dynamic`, ya no se tendra el error de tipo diferente.

este tipo de declaracion nos sirve para declarar una variable que en el futuro pueda que cambie de tipo, pero como se indica en un inicio, por buena practicas, es mejor preferir el tipado fuerte, y desde la logica visualizar esos casos y manejarlos de un modo diferente

-   [Replit - tipado dinamico](https://repl.it/@JairoLopez2/tipado-dinamico#main.dart)

```dart
void main() {
    dynamic nameVar = 45;
    print('${nameVar} es tipo ${nameVar.runtimeType}');
    nameVar = 45.6;
    print('${nameVar} es tipo ${nameVar.runtimeType}');
    nameVar = "jairo";
    print('${nameVar} es tipo ${nameVar.runtimeType}');
    nameVar = true;
    print('${nameVar} es tipo ${nameVar.runtimeType}');
}
```
