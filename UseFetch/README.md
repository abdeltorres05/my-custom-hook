#useFetch
El hook toma un parámetro obligatorio llamado "url" que representa la URL de la API a la que se realizará la solicitud.

Dentro del hook, se utiliza el hook useState para crear una variable de estado llamada "state" que contiene tres propiedades: "data", "loading" y "error". El valor inicial de "state" es un objeto con "data" establecido en null, "loading" establecido en true y "error" establecido en null.

También se utiliza el hook useRef para crear una referencia mutable llamada "isMounted" que se utiliza para verificar si el componente está montado o no. Esto es necesario para evitar errores de actualización del estado en componentes desmontados.

Se utilizan dos useEffect. El primero se ejecuta solo una vez al montar el componente y su función de retorno se ejecuta cuando el componente se desmonta. En la función de retorno, se establece "isMounted.current" en false para indicar que el componente está desmontado.

El segundo useEffect se ejecuta cada vez que cambia la "url". En este useEffect, se establece el estado inicial de "state" antes de realizar la solicitud de API. Luego, se realiza la solicitud de API utilizando la función fetch. Una vez que se recibe la respuesta, se verifica si el componente está montado antes de actualizar el estado con los datos recibidos. Si el componente está desmontado, no se actualiza el estado.

Finalmente, el hook devuelve el estado actualizado que contiene los datos, el estado de carga y cualquier error que pueda haber ocurrido durante la solicitud de API. Este hook puede ser utilizado en componentes de función de React para realizar solicitudes de API y manejar el estado de la respuesta.