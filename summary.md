Se realizaron los siguientes cambios clave para implementar la manipulación de texto entre componentes Blazor:

1.  **`LirmiDemoApp.Client/Pages/TextTestPageComponent.razor`**:
    *   Se actualizó para incluir un campo de entrada (`<input type="text">`) que permite al usuario ingresar texto.
    *   Captura el texto ingresado y lo pasa como un parámetro (`TextToManipulate`) a una instancia de `TextManipulatorComponent`.

2.  **`LirmiDemoApp.Client/Shared/TextManipulatorComponent.razor`**:
    *   Se creó este componente compartido, el cual expone un `[Parameter]` llamado `TextToManipulate`.
    *   En el método `OnParametersSet()`, el componente toma el valor de `TextToManipulate`, lo convierte a mayúsculas y almacena el resultado.
    *   Finalmente, renderiza tanto el texto original recibido como su versión en mayúsculas.

En resumen, se estableció un flujo donde un componente de página recolecta una entrada de texto y la delega a un componente compartido para su procesamiento (conversión a mayúsculas) y visualización.