## Ciclo de vida de los componentes en Vue.
Cada componente es una instancia de un componente de Vue los cuales están cambiando periódicamente. en algún momento los componentes son creados o destruidos cuando estos salen del DOM. Vue nos ofrece funciones para ejecutar código antes de que un componente se monte o después de que este se haya retirado del DOM.

Como traer datos cuando se renderiza, un componente y rellenarlo con esos datos.

los hooks del ciclo de vida son:
beforeCreate Se llama cuando la instancia se inicializa, después de que las props se resuelven y antes de procesar opciones como data() o computed

beforeCreate(){
  //código a ejecutar
}
created se llama cuando la instancia ha terminado de procesar todas las opciones relacionados con el estado, como lo son: datos reactivos, propiedades computadas, métodos y observadores, pero aún no comienza la fase de montado y la función $el aún no esta disponible.

created(){
  //lógica a ejecutar
}
beforeMount Se llama cuando el componente ha sido montado, pero no existen nodos en el DOM aún, pero están a punto de ser ejecutado el render el DOM por primera vez, no se llama su usamos renderizado del lado de servidor.

beforeMount(){
  //lógica  a ejecutar
}
mounted Se llama cuando el componente ha sido montado, se considera montado cuando: todos sus componentes hijos síncronos han sido montados, no se incluyen los asíncronos o los que estén en modo suspendido <Suspense> , cuando su propio árbol del DOM ha sido creado e insertado en su contenedor padre. Tampoco es llamado durante renderizado del lado del servidor

mounted(){
  //logica a ejecutar
}
beforeUpdate Se llama justo cuando el componente esta por actualizar su árbol del DOM, debido a un cambio reactivo. Este hook se puede usar para acceder al DOM justo cuando Vue esta por hacer un cambio.

beforeUpdate(){
  //logica a ejecutar
}
updated Se llama justo cuando el componente ha sido actualizado por un cambio en su estado, En caso del padre su método se llamará cuando los métodos de sus hijos hayan terminado. Es importante tener cuidado si no somos precavidos podemos provocar ciclos de renderizado infinito.

updated(){
  //logica a ejecutar
}
beforeUnmount Se llama justo cuando la instancia esta por salir del DOM, cuando usamos este hook la instancia que esta por salir aun es funcional

beforeUnmount(){
  //logica a ejecutar
}
unmounted se llama cuando el componente es desmontado, un componente se considera desmontado cuando: todos su hijos han sido desmontados y todos sus efectos reactivos se han detenido, este hook se utiliza cuando queremos limpiar de manera manual algunos efectos como cuentas regresivas, conexiones con el server o eventos del DOM.

unmounted(){
  //logica a ejecutar
}
Todas se colocan dentro del objeto de configuración de la option API como una opción más.

## Mixins
permiten reutilizar codigo  
## Options API o Composition API ¿Cuál elegir?

Ambos estilos de API son totalmente capaces de cubrir casos de uso comunes. Son interfaces diferentes impulsadas por el mismo sistema. De hecho, ¡la API de opciones se implementa sobre la API de composición! Los conceptos y conocimientos fundamentales sobre Vue se comparten entre los dos estilos.

La API de opciones se centra en el concepto de una “instancia de componente”, que generalmente se alinea mejor con un modelo mental basado en clases para usuarios que provienen de entornos lingüísticos de programación orientada a objetos. También es más amigable para principiantes al abstraer los detalles de reactividad y hacer cumplir la organización del código a través de grupos de opciones.

La API de composición se centra en declarar variables de estado reactivas directamente en el ámbito de una función y componer el estado de varias funciones juntas para manejar la complejidad. Tiene una forma más libre y requiere una comprensión de cómo funciona la reactividad en Vue para ser utilizado de manera efectiva. A cambio, su flexibilidad permite patrones más poderosos para organizar y reutilizar la lógica.

Puede obtener más información sobre la comparación entre los dos estilos y los posibles beneficios de la API de composición en las Preguntas frecuentes sobre la API de composición.

Si es nuevo en Vue, esta es nuestra recomendación general:

Para propósitos de aprendizaje, elige el estilo que te parezca más fácil de entender. Una vez más, la mayoría de los conceptos básicos se comparten entre los dos estilos. Siempre puedes elegir el otro estilo más tarde.

Para uso en producción:

Vaya con la API de opciones si no está utilizando herramientas de compilación o planea usar Vue principalmente en escenarios de baja complejidad, p. mejora progresiva.

Elija Composición API + Componentes de un solo archivo si planea crear aplicaciones completas con Vue.

No tienes que comprometerte con un solo estilo durante la fase de aprendizaje. La documentación de Vue proporcionará ejemplos de código en ambos estilos cuando corresponda, y puede alternar entre ellos en cualquier momento utilizando los interruptores de preferencia de API en la parte superior de la barra lateral izquierda en la página de la documentación oficial de Vue.js

## Watch
 son funciones que nos permiten escuchar cuando una variable reactiva cambian y podemos acceder a su valor antiguo y a su valor nuevo

## computed
