Se han realizado mejoras significativas en dos componentes UI clave, enfocándose en la **parametrización y flexibilidad**:

*   **`SkeletonComponent.razor`:**
    *   Se han introducido nuevos `[Parameter]` para `Width`, `Height` y `Shape`.
    *   Esto permite una mayor personalización del tamaño y la forma de los esqueletos de carga, adaptándose dinámicamente según los valores proporcionados y mejorando la flexibilidad visual.

*   **`UiSwitch.razor`:**
    *   Se ha extendido la funcionalidad con varios `[Parameter]` nuevos:
        *   `IsChecked`: Para gestionar el estado actual del interruptor.
        *   `IsCheckedChanged`: Un `EventCallback` para implementar two-way binding y notificar cambios de estado.
        *   `Text`: Para una etiqueta o descripción asociada al interruptor.
        *   `Color`: Para personalización visual del interruptor.
        *   `Disabled`: Para controlar la interactividad del componente.
    *   Esto lo convierte en un control de interruptor más robusto y configurable.