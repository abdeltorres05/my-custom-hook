#Notas

Este repositorio contiene varios cutom hooks que pueden ser utiles

#useCounter
El hook "useCounter" toma un parámetro opcional llamado "initialState" con un valor predeterminado de 10. Este parámetro se utiliza para establecer el estado inicial del contador.

Dentro del hook, se utiliza el hook useState para crear una variable de estado llamada "counter" y una función para actualizarla llamada "setCounter". El valor inicial del estado se establece en el valor pasado como parámetro o en 10 si no se proporciona ningún valor.

El hook devuelve un objeto con cuatro propiedades: "counter", "increment", "reset" y "decrement". 

- La propiedad "counter" contiene el valor actual del contador.
- La función "increment" incrementa el valor del contador en 1 al llamar a la función "setCounter".
- La función "reset" restablece el valor del contador al estado inicial al llamar a la función "setCounter" con el valor inicial.
- La función "decrement" decrementa el valor del contador en 1 al llamar a la función "setCounter".

Este hook puede ser utilizado en componentes de función de React para gestionar el estado de un contador y realizar operaciones como incrementar, decrementar y restablecer su valor.

#useFetch
El hook toma un parámetro obligatorio llamado "url" que representa la URL de la API a la que se realizará la solicitud.

Dentro del hook, se utiliza el hook useState para crear una variable de estado llamada "state" que contiene tres propiedades: "data", "loading" y "error". El valor inicial de "state" es un objeto con "data" establecido en null, "loading" establecido en true y "error" establecido en null.

También se utiliza el hook useRef para crear una referencia mutable llamada "isMounted" que se utiliza para verificar si el componente está montado o no. Esto es necesario para evitar errores de actualización del estado en componentes desmontados.

Se utilizan dos useEffect. El primero se ejecuta solo una vez al montar el componente y su función de retorno se ejecuta cuando el componente se desmonta. En la función de retorno, se establece "isMounted.current" en false para indicar que el componente está desmontado.

El segundo useEffect se ejecuta cada vez que cambia la "url". En este useEffect, se establece el estado inicial de "state" antes de realizar la solicitud de API. Luego, se realiza la solicitud de API utilizando la función fetch. Una vez que se recibe la respuesta, se verifica si el componente está montado antes de actualizar el estado con los datos recibidos. Si el componente está desmontado, no se actualiza el estado.

Finalmente, el hook devuelve el estado actualizado que contiene los datos, el estado de carga y cualquier error que pueda haber ocurrido durante la solicitud de API. Este hook puede ser utilizado en componentes de función de React para realizar solicitudes de API y manejar el estado de la respuesta.

#useForm
El hook toma un parámetro opcional llamado "initialState" que representa el estado inicial del formulario. Si no se proporciona ningún estado inicial, se utilizará un objeto vacío.

Dentro del hook, se utiliza el hook useState para crear una variable de estado llamada "value" que contiene el estado actual del formulario. El valor inicial de "value" es el estado inicial proporcionado.

El hook también define dos funciones: "reset" y "handleInputChange". La función "reset" se utiliza para restablecer los valores del formulario a su estado inicial. Esto se logra llamando a la función setValue y pasando el estado inicial como argumento.

La función "handleInputChange" se utiliza para cambiar los valores de los campos del formulario cuando se produce un evento de cambio. Esta función toma un parámetro llamado "target" que representa el elemento HTML que generó el evento de cambio. Dentro de la función, se utiliza la función setValue para actualizar el estado del formulario. Se utiliza la sintaxis de propagación (...) para copiar el estado actual del formulario y luego se cambia el valor del campo correspondiente utilizando la propiedad "name" del elemento HTML y el valor del campo utilizando la propiedad "value" del elemento HTML.

Finalmente, el hook devuelve un arreglo que contiene el estado actual del formulario, la función "handleInputChange" para cambiar los valores de los campos del formulario y la función "reset" para restablecer los valores a su estado inicial. Este hook puede ser utilizado en componentes de función de React para manejar el estado de un formulario.