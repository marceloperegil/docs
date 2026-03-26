Este resumen describe los cambios clave relacionados con la seguridad y OAuth2:

1.  **Dependency Migration:** Actualizado el `pom.xml` para migrar de `spring-security-oauth2` (deprecated) a los nuevos `spring-boot-starter-oauth2-resource-server` y `spring-boot-starter-oauth2-client`.
2.  **OAuth2 Resource Server:** Configurada la aplicación (`WebSecurityConfig`) para actuar como un OAuth2 Resource Server, validando JWTs entrantes contra un JWKS URI externo (especificado en `application.properties`).
3.  **API Authorization:** Se implementó control de acceso basado en scopes (ej. `SCOPE_internal`) para proteger rutas como `/clients/**` y `/users/**`, asegurando que solo tokens con la autoridad requerida puedan acceder.
4.  **Authorization Server (Legacy):** Las configuraciones del Authorization Server (`AuthorizationServerConfig`) y la gestión de clientes (`Client` entity, `ClientRepository`, `ClientService`) se mantienen utilizando las interfaces y clases del antiguo Spring Security OAuth2 (`ClientDetails`).
5.  **Seguridad General:** Habilitado CORS, deshabilitado CSRF y configurado el acceso a la consola H2.
6.  **Sesiones Stateless:** Se configuró la gestión de sesiones como `STATELESS`, acorde con las mejores prácticas de API REST y OAuth2.

En resumen, la aplicación ahora funciona como un **Resource Server moderno** (validando JWTs del nuevo stack) mientras que sus **componentes de Authorization Server** para la gestión de clientes aún utilizan el stack legacy de Spring Security OAuth2.