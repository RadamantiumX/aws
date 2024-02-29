# LAMBDA

Nos permite ejecutar codigo sin la necesidad de levantar un servidor virtual. Tienen muy poca latencia, al tratarse de pequeñas funciones.

Las dependencias instaladas en la LAMBDA FUNCTION no deben sobrecargar la misma, el propósito es que sean lo mas ágiles posibles en ejecución.

Un ejemplo de una LAMBDA FUNCTION:

```javascript
export const handler = async (event) => {
  // TODO implement
  const response = {
    statusCode: 200,
    body: JSON.stringify('Hello from Lambda!'),
  };
  return response;
};

```
Es un funcion asincrona, en la cual, segun el codigo, devuelve un JSON en el **body**.

*❗IMPORTANTE: Las LAMBDA tienen un coste por tiempo de ejecución, si las sobrecargamos y tardan mas de lo q deberian en ejecutarce, se nos facturara un valor por ese servicio.*

Lo siguiente sería crear una funcion para verificar si esta ONLINE o NO, en TWITCH. EN este caso vamos a utilizar una API, para evitar toda la logica que convella realizar esa acción.

```javascript
export const handler = async (event) => {
  const user = "radamantium1"
  console.log({ user })
  
  const res = await fetch(`https://midudev-apis.midudev.workers.dev/uptime/${user}`)
  const { online } = await res.json()
  const response = {
    statusCode: 200,
    body: JSON.stringify({ online }),
  };
  return response;
};
```

Al realizar un cambio en la función, debemos darle al botón *DEPLOY*, para que se apliquen los cambios realizados.

Las LAMBDA FUNCTIONS las podemos ejecutar como si fueran API's, con tan solo una URL, pero, también, segun cuando ocurra algo.


## DESENCADENADORES

Las funciones se ejecutaran cuando ocurra algo. Por ejemplo, cuando se reciba un email, cuando hable con ALEXA, cuando se hace un **commit** aun sitio, y hay muchos mas TRIGGERS para las LAMBDA FUNCTIONS. Un ejemplo básico sería: Cuando un usuario hace una compra a traves de SHOPIFY, automaticamente con una LAMBDA FUNCTION se le envia un mail.

El resultado de una LAMBDA FUNCTION podemos enviarlo a un destino.