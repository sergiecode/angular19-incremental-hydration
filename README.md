
#### ¿QUÉ ES LA HIDRATACIÓN INCREMENTAL?

La hidratación incremental es una nueva funcionalidad de Angular 19 diseñada para optimizar el renderizado del lado del servidor (SSR). Permite que ciertas partes de la aplicación se hidraten (se vuelvan interactivas) solo cuando se cumplen condiciones específicas. Esta mejora se basa en estrategias previas de Angular, como la hidratación completa de la aplicación o la hidratación diferida de vistas.

**Resultado:**  
La hidratación incremental reduce el tamaño de los paquetes de JavaScript y acelera la carga inicial, mejorando el rendimiento y la experiencia del usuario.

----------

#### DIFERENCIA CON LA HIDRATACIÓN COMPLETA DE LA APLICACIÓN

1.  **Hidratación completa:**
    
    -   Hidrata toda la aplicación de una sola vez, requiriendo cargar todo el JavaScript desde el inicio.
    -   Puede generar tiempos de carga inicial más lentos debido al tamaño del paquete.
2.  **Hidratación incremental:**
    
    -   Hidrata partes de la app de manera dinámica, según disparadores como la interacción del usuario o la visibilidad.
    -   Minimiza la cantidad de JavaScript cargado inicialmente.

----------

#### IDEA PRINCIPAL

Renderizar todo en el servidor para ofrecer una experiencia visual completa, pero diferir la hidratación en el cliente hasta que sea realmente necesaria.

**Disparadores de hidratación:**

-   **Visibilidad:** Cuando el contenido entra en el viewport.
-   **Interacción:** Cuando el usuario hace clic o interactúa con el elemento.
-   **Temporizador:** Después de un retraso predefinido.
-   **Hover:** Cuando el usuario pasa el cursor sobre el contenido.
-   **Nunca:** El contenido permanece estático y no se hidrata.

----------

#### BENEFICIOS DE LA HIDRATACIÓN INCREMENTAL

1.  **Tiempos de carga inicial más rápidos**
    
    -   Reduce la cantidad de JavaScript enviado al cliente.
    -   Prioriza el contenido esencial para un renderizado más veloz.
2.  **Mejor experiencia de usuario**
    
    -   Evita cambios de diseño o parpadeos durante la hidratación.
    -   Garantiza que la aplicación sea fluida y responsiva.
3.  **Uso eficiente de recursos**
    
    -   Aprovecha los recursos del servidor para el renderizado, aliviando la carga en el cliente.
    -   Mejora el rendimiento en dispositivos con recursos limitados.
4.  **Comportamiento personalizable**
    
    -   Los desarrolladores pueden decidir cuándo y cómo deben hidratarse partes específicas de la app.
    -   Proporciona flexibilidad para priorizar componentes críticos o de uso frecuente.
5.  **Optimización para SEO**
    
    -   Permite que los motores de búsqueda indexen contenido mientras se minimiza el uso de JavaScript.

----------

#### FUNCIONALIDADES AVANZADAS DE LA HIDRATACIÓN INCREMENTAL

1.  **Disparador "Nunca"**
    
    -   Uso: Contenido estático que no requiere interactividad, como publicaciones de blog.
2.  **Disparador "Hover"**
    
    -   Uso: Elementos interactivos como tooltips o menús que se hidratan al pasar el cursor.
3.  **Combinación de disparadores**
    
    -   Los desarrolladores pueden utilizar múltiples disparadores para lógica de hidratación más compleja.

----------

#### INTEGRACIÓN CON REPRODUCCIÓN DE EVENTOS

**¿Qué es la reproducción de eventos?**  
Es una funcionalidad que captura las interacciones del usuario (como clics o entradas de formularios) en componentes deshidratados y las reproduce cuando se hidratan.

**¿Por qué es necesaria?**

-   En SSR, el HTML renderizado puede parecer interactivo, pero no lo es hasta que se carga el JavaScript.
-   Las acciones del usuario podrían perderse si interactúa antes de la hidratación.
-   La reproducción de eventos asegura que todas las interacciones sean capturadas y procesadas, garantizando una experiencia fluida.
