#useCounter
El hook "useCounter" toma un parámetro opcional llamado "initialState" con un valor predeterminado de 10. Este parámetro se utiliza para establecer el estado inicial del contador.

Dentro del hook, se utiliza el hook useState para crear una variable de estado llamada "counter" y una función para actualizarla llamada "setCounter". El valor inicial del estado se establece en el valor pasado como parámetro o en 10 si no se proporciona ningún valor.

El hook devuelve un objeto con cuatro propiedades: "counter", "increment", "reset" y "decrement". 

- La propiedad "counter" contiene el valor actual del contador.
- La función "increment" incrementa el valor del contador en 1 al llamar a la función "setCounter".
- La función "reset" restablece el valor del contador al estado inicial al llamar a la función "setCounter" con el valor inicial.
- La función "decrement" decrementa el valor del contador en 1 al llamar a la función "setCounter".

Este hook puede ser utilizado en componentes de función de React para gestionar el estado de un contador y realizar operaciones como incrementar, decrementar y restablecer su valor.