# EXAMEN DE RECUPERACIÓN – DWES

**Entrega:** 
- Repositorio Git con commits progresivos y significativos. **Cada avance o funcionalidad se debe trabajar en una rama distinta que se mergeará a main.**
- Vídeo de las tablas con datos en el panel de administración de Django
- Vídeo de la prueba de los endpoints en Postman.
  - Incluye al menos 3 ejemplos que muestren el filtrado combinado, orden y paginación.
       
**Objetivo:** Desarrollar una API REST funcional en Django con SQLite. Los datos deberán ser introducidos previamente desde el panel de administración. Se requiere el uso de autenticación, relaciones, consultas avanzadas y documentación.

## PARTE 1: Configuración inicial 

- Crea un proyecto Django llamado `api_tienda` y una app llamada `productos`.
- Usa SQLite como sistema de base de datos.
- Registra la app en `INSTALLED_APPS`.
- Crea un superusuario y accede correctamente al panel de administración (`/admin`).

## PARTE 2: Modelos y administración 
- Define un modelo `UsuarioPersonalizado`.
- Añade al menos dos campos adicionales: por ejemplo, `telefono` y `direccion`.
- Define tres modelos:
  - `Categoria`: campo `nombre`.
  - `Producto`: campos `nombre`, `descripcion`, `precio`, `stock`, y relación con `Categoria`.
  - `Proveedor`: campo `nombre`, relacionado con uno o varios productos.

- El modelo `Producto` debe incluir un método para calcular un precio con descuento.
- Registra los tres modelos en el panel de administración.
- Introduce al menos 3 categorías, 5 productos y 2 proveedores. Los productos deben estar correctamente asociados.
- Los usuarios se generarán desde la API.

## PARTE 3: API REST con APIView

Implementa los siguientes endpoints mediante clases basadas en `APIView`. Todas las respuestas deben devolverse en formato JSON. Se requiere el uso de `select_related`, `Q`, `F`, `aggregate`, paginación, y control de autenticación mediante token.
- `POST /registro/`
  El endpoint permite registrar nuevos usuarios personalizados desde la API.
  Debe validar correctamente los campos requeridos y devolver una respuesta clara.

- `POST /api-token-auth/` 
  Permite a los usuarios obtener un token con sus credenciales.
  
- `GET /productos/`  
  Lista de productos con datos completos de su categoría y proveedor. Usa `select_related` para optimizar el acceso a relaciones.

- `GET /productos/<int:id>/`  
  Devuelve el detalle de un producto, incluyendo sus relaciones. En este endpoint debe usarse una comparación entre campos del modelo mediante `F`.

- `POST /productos/`  
  Crea un nuevo producto. Este endpoint requiere autenticación con token. Valida correctamente las relaciones.

- `PUT /productos/<int:id>/`  
  Modifica un producto existente. Solo accesible para usuarios autenticados mediante token.

- `DELETE /productos/<int:id>/`  
  Elimina un producto existente. Requiere autenticación.

- `GET /buscar/`  
  Devuelve productos filtrados por nombre (mediante condiciones OR), con posibilidad de ordenación y límite de resultados. Debe usarse `Q` para combinar condiciones y paginación para limitar los resultados. Además, la vista debe devolver:
  - El precio medio de los productos (usando `Avg`).
  - La suma total de stock (`Sum`).
  - 
- Los endpoints de creación, edición y eliminación deben estar protegidos por autenticación mediante token (`TokenAuthentication`) usando una clase de permisos.

## PARTE 4: Documentación 
  
- Documenta la API con **Swagger** (`drf-yasg`):
  - Cada endpoint debe mostrar su descripción, parámetros y cuerpos de solicitud.

## RÚBRICA DE EVALUACIÓN

| Aspecto                                                                                     | Puntos |
|---------------------------------------------------------------------------------------------|--------|
| **Configuración del proyecto**                                                              | 0.25    |
| - Proyecto creado, app registrada, superusuario funcional                                   |        |
|                                                                                             |        |
| **Modelado de datos**                                                                       | 0.5    |
| - Modelos correctamente definidos y relacionados                                            | 0.4    |
| - Datos introducidos en admin (categorías, productos, proveedores)                         | 0.1    |
|                                                                                             |        |
| **API REST – Endpoints (con APIView)**                                                      | 6.0    |
| - `POST /registro/`: registro funcional de usuario                                                | 0.5   |
| - `GET /productos/`: uso de `select_related`                                                | 1.0   |
| - `GET /productos/<id>/`: uso de `F`                                                        | 1.0   |
| - `POST /productos/`: autenticación y validación de relaciones                              | 1.0   |
| - `PUT`, `DELETE`: control de acceso, correcto funcionamiento                              | 0.5    |
| - `GET /buscar/`: combinación de filtros con `Q`, ordenación y paginación                   | 1.0    |
| - `GET /buscar/`: inclusión de `aggregate` (`Avg`, `Sum`)                                   | 1.0   |
|                                                                                             |        |
| **Autenticación y permisos**                                                                | 1.25    |
| - Token funcional, vistas protegidas, permisos aplicados correctamente                      |        |
|                                                                                             |        |
| **Documentación (Swagger)**                                                                 | 1.0    |
| - Endpoints bien descritos, incluyendo parámetros y cuerpos                                 |        |
|                                                                                             |        |
| **Control de versiones (Git)**                                                              | 1.0  |
| - Commits progresivos, claros y descriptivos                                                |   0.5  |
| - Cada endpoint en una rama                                                                 |   0.5  |
| - Las ramas se mergean a main mediante pull request                                         |   0.5  |
|                                                                                             |        |
| **TOTAL**                                                                                    | **10** |
