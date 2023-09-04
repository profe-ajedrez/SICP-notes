# Proceso recursivo proceso iterativo


* _Una función es un patrón para la evolución local de un proceso computacional._

### Recursión lineal e iteración.

 - factorial recursivo:

```javascript
function factorial(n) {
    return n === 1 ? 1 : n * factorial(n -1);
}
```

- factorial iterativo:

```javascript

function f_iter(p,c, m) {
    return z > m ? p : f_iter(c * p, c + 1, m);
}

function factorial(n) {
    return f_iter(1, 1, a);
}
```


Notese que si bien ambos procesos usan la *técnica* de la recursión, solo el primero es un *proceso* recursivo, el segundo es un proceso iterativo.


- Modelos de sustitución:

Ejemplo factorial recursivo:


* Se forma una cadena de *operaciones deferidas* porque se debe esperar a que se resuelva la última de la cadena.

* La expansión de la forma se detiene cuando las operaciones empiezan a realizarse efectivamente.

* La máquina debe mantener registro de  las operaciones que se ejecutyarán después.

* El largo de la cadena de operaciones deferidas  crece linealmente con n, al igual que el número de pasos. Se le llama a esto ***proceso lineal recursivo***

```
factorial(6)
6 * factorial(5)
6 * (5 * factorial(4))
6 * (5 * (4 * factorial(3)))
6 * (5 * (4 * (3 * factorial(2))))
6 * (5 * (4 * (3 * (2 * factorial(1)))))
6 * (5 * (4 * (3 * (2 * 1))))
6 * (5 * (4 * (3 * 2 )))
6 * (5 * (4 * 6))
6 * (5 * 24)
6 * 120
720
```

Ejemplo factorial iterativo:

* No crece ni se contrae.

* Solo se mantiene registro del valor del producto, el paso en curso y el máximo n en cada paso.

* Llamamos a esto ***proceso lineal iterativo***

```
factorial(6)
f_iter(1, 1, 6)    
f_iter(1, 2, 6)
f_iter(2, 3, 6)
f_iter(6, 4, 6)
f_iter(24, 5, 6)
f_iter(120, 6, 6)
f_iter(720, 7, 6)
720
```


En el ejemplo iterativo,  las variables proveen una completa descripción del **estado del proceso**
En el ejemplo recursivo, se mantiene cierta información coculta, mantenida por la máquina la cual no está contenida en las variables de estado.
Mientras mas larga la cadena de operaciones deferidas, mas  información debe ser mantenida.

