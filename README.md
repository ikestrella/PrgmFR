# **PROGRAMACIÓN REACTIVA**
La programación reactiva se enfoca en el manejo de flujos de datos asíncronos, es decir, datos que no están sincronizados con el flujo principal de datos. Se basa en el uso de observables y flujos de datos.

Los flujos de datos son datos que cambian a lo largo del tiempo y que normalmente son de interés para observar, ya que tienen actualizaciones constantes.

Los datos asíncronos son aquellos que se transfieren entre dispositivos que no transmiten a la misma velocidad entre ellos. Estos datos pueden enviarse en cualquier momento, lo cual es una ventaja, ya que pueden utilizarse tan pronto como estén disponibles en lugar de esperar a que se complete una solicitud antes de pasar a la siguiente.


<p align="center">
  <img src="https://github.com/ikestrella/PrgmFR/assets/116619952/2c63fabd-395a-47fc-b7ee-4ca26f0c7c27" />
</p>



## **MANIFIESTO REACTIVO**
Los sistemas reactivos deben cumplir con los siguientes principios del Manifiesto Reactivo:

* **Responsivos**: Deben responder de manera oportuna y adecuada, gestionando los errores de manera apropiada. La responsividad es la base de la utilidad y usabilidad de los sistemas.

* **Resilientes**: Tienen tolerancia y recuperación ante fallos. Mantienen la responsividad incluso cuando el sistema falla.

* **Elásticos**: Tienen la capacidad de expandirse según la demanda. La responsividad se mantiene incluso con el aumento de la carga de trabajo.

* **Orientados a Mensajes**: La comunicación entre componentes se basa en el intercambio de mensajes asíncronos para evitar el acoplamiento y mejorar el aislamiento.

Los sistemas reactivos deben ser altamente responsivos y capaces de adaptarse de forma dinámica a los cambios en los flujos de datos y eventos que ocurren en tiempo real.

## **PATRÓN OBSERVER**

Un observer representa a los suscriptores a los eventos emitidos por los observables. Mediante los observers, se pueden obtener los diferentes cambios que los flujos de datos experimentan en un momento en particular, es decir, se observan los flujos de datos y sus cambios.

* **Observable**: secuencia de eventos que se pueden observar a medida que ocurren. Es el encargado de proporcionarnos datos.

## **VENTAJAS**
Los beneficios de la programación reactiva incluyen:

* Mejoras en la experiencia del usuario.

* Permite a las aplicaciones responder de manera eficiente a los eventos.

* Mantiene tiempos de respuesta rápidos.

* Alta capacidad de adaptación (rendimiento del código).

## **DESVENTAJAS**
Las desventajas de este paradigma de programación incluyen:

* Puede consumir más memoria, aunque puede ser más eficiente.

* Se necesita de librerías específicas, lo cual implica una dependencia de terceros para el desarrollo de una aplicación.

* Se requiere de herramientas y técnicas especiales para facilitar la identificación y resolución de problemas.

## **FRAMEWORKS REACTIVOS**
* React.js

* RxJava

* RxJS

* Vue.js

## **OPERADORES**
Los operadores son funciones de alto orden que nos permiten manipular y transformar los datos que fluyen a través de los publicadores. Los publicadores son componentes observables encargados de publicar información en el flujo de datos.

Los operadores son esenciales para realizar operaciones como filtrado, mapeo, combinación, etc.

## **EJEMPLO DE PROGRAMACIÓN REACTIVA**

Ejemplo sencillo de programación reactiva en JavaScript. Crearemos un observable que emitirá un evento cada vez que se haga clic en el documento. Este evento será observado y manejado por un observer.


```
//Biblioteca
const { fromEvent } = require('rxjs');

// Observable
const clicks = fromEvent(document, 'click');

// Observer
const observer = {
 
  next: event => console.log(`Haz hecho clic en las coordenadas: ${event.clientX}, ${event.clientY}`),
  
  error: err => console.error('Algo salió mal: ' + err),
  
  complete: () => console.log('¡Terminado!'),
};

// Suscripcion del Observer al Observable
clicks.subscribe(observer);
```

