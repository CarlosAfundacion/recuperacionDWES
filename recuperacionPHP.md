### **Práctica Integradora: Gestión de una Biblioteca Online**  
 **Duración estimada:** 90 minutos  
 **Objetivo:** Desarrollar una aplicación web que permita a los usuarios registrarse, iniciar sesión, ver un catálogo de libros y solicitar préstamos de libros.  

---

## **Descripción General del Proyecto**  
Se desarrollará una aplicación web donde los usuarios podrán registrarse en la plataforma, iniciar sesión, ver un catálogo de libros y solicitar préstamos. Cada usuario podrá ver los libros disponibles y seleccionar uno para solicitar su préstamo. Se utilizará una base de datos para almacenar la información de usuarios, libros y préstamos.  

---

## **Estructura del Proyecto**  

El proyecto estará compuesto por los siguientes archivos y funcionalidades:  

1. **Base de Datos**: Creación de las tablas necesarias para la gestión de usuarios, libros y préstamos.  
2. **Registro de Usuarios**: Un formulario que permita a los usuarios registrarse en la plataforma.  
3. **Inicio de Sesión**: Un formulario donde los usuarios puedan autenticarse con su email y contraseña.  
4. **Listado de Libros**: Una página que muestra los libros disponibles en la biblioteca.  
5. **Solicitud de Préstamo**: Un formulario para que los usuarios registrados puedan solicitar un libro.  
6. **Cierre de Sesión**: Opción para que los usuarios puedan cerrar sesión.  

---

## **Parte 1: Creación de la Base de Datos**  

- Se debe crear una base de datos llamada `biblioteca_db`.  
- En la base de datos, deben existir las siguientes tablas:  
  - `usuarios`: Para almacenar la información de los usuarios registrados.  
  - `libros`: Para registrar los libros disponibles en la biblioteca.  
  - `prestamos`: Para llevar el control de los libros prestados a los usuarios.  
- Se deben definir las relaciones entre las tablas, asegurando que los préstamos están asociados a un usuario y un libro.  
- Se deben insertar datos de prueba en cada tabla para facilitar las pruebas.  

---

## **Parte 2: Registro de Usuarios**  

- Se debe crear una página `registro.php` con un formulario donde los usuarios puedan registrarse proporcionando su **nombre, email y contraseña**.  
- Al completar el registro, los datos deben almacenarse en la base de datos y el usuario debe recibir un mensaje confirmando el registro.  
- Una vez registrado, el usuario debe ser redirigido a la página de inicio de sesión (`login.php`).  

---

## **Parte 3: Inicio de Sesión**  

- Se debe crear una página `login.php` donde los usuarios puedan ingresar su **email y contraseña** para acceder a la plataforma.  
- Si las credenciales son correctas, el usuario debe ser redirigido a la página principal de la aplicación (`listado_libros.php`).  
- Si las credenciales son incorrectas, debe mostrarse un mensaje de error.  
- Al iniciar sesión, debe almacenarse la información del usuario en una sesión para identificarlo en futuras interacciones.  

---

## **Parte 4: Listado de Libros**  

- Se debe crear una página `listado_libros.php` donde se muestren los libros disponibles en la biblioteca.  
- La página debe presentar una tabla con la siguiente información de cada libro: **título, autor y año de publicación**.  
- Si el usuario **no ha iniciado sesión**, debe mostrarse un mensaje indicando que debe autenticarse antes de poder solicitar un préstamo.  
- Si el usuario **ha iniciado sesión**, cada libro debe mostrar un botón de **"Solicitar préstamo"**, que redirija a la página `prestamos.php` con la información del libro seleccionado.  

---

## **Parte 5: Solicitud de Préstamo**  

- Se debe crear una página `prestamos.php` donde el usuario pueda solicitar el préstamo de un libro.  
- La página debe mostrar la información del libro seleccionado y un botón para confirmar el préstamo.  
- Al confirmar, el préstamo debe registrarse en la base de datos con la **fecha actual** y el usuario debe ser redirigido de vuelta a la página `listado_libros.php`, donde debe mostrarse un mensaje de éxito.  
- Un usuario solo puede solicitar un libro si **ha iniciado sesión**. Si intenta acceder sin estar autenticado, debe ser redirigido a `login.php`.  

---

## **Parte 6: Cierre de Sesión**  

- Se debe crear una página `logout.php` que cierre la sesión del usuario y lo redirija de vuelta a la página de inicio de sesión (`login.php`).  
- Una vez cerrada la sesión, si el usuario intenta acceder a `listado_libros.php` o `prestamos.php`, debe ser redirigido a `login.php` automáticamente.  

---

## **Requisitos Adicionales**  

- **Validación de Datos:** Se debe validar que los campos obligatorios no estén vacíos en los formularios de registro y login.  
- **Seguridad:**  
  - Las contraseñas de los usuarios no deben almacenarse en texto plano.  
  - No debe ser posible acceder a páginas protegidas sin haber iniciado sesión.  
  - Se deben prevenir inyecciones SQL al manejar datos de entrada del usuario.  

---

## **Flujo de Navegación entre Páginas**  

1. El usuario accede a `registro.php` y se registra.  
2. Tras registrarse, es redirigido automáticamente a `login.php`.  
3. El usuario introduce sus credenciales en `login.php`.  
4. Si las credenciales son correctas, es redirigido a `listado_libros.php`.  
5. En `listado_libros.php`, el usuario puede ver los libros disponibles.  
6. Si el usuario desea solicitar un libro, hace clic en "Solicitar préstamo" y es llevado a `prestamos.php`.  
7. En `prestamos.php`, el usuario confirma el préstamo y es redirigido nuevamente a `listado_libros.php`.  
8. En cualquier momento, el usuario puede cerrar sesión mediante `logout.php`, lo que lo redirige a `login.php`.  
9. Si el usuario intenta acceder a `listado_libros.php` o `prestamos.php` sin iniciar sesión, será redirigido a `login.php`.  

---


## **Entrega**

- Sube tu código a classroom a un archivo comprimido con tu nombre y apellido.
- Sube un vídeo probando todas las funcionalidades implementadas
- Sube un archivo SQL con todos los datos de tu aplicación.

---

## **Criterios de Evaluación**  

 **Funcionamiento Correcto:** La aplicación debe permitir el registro, inicio de sesión, listado de libros y solicitud de préstamos.  
 **Seguridad:** Se debe proteger el acceso a páginas privadas y almacenar las contraseñas de forma segura.  
 **Organización del Código:** El código debe estar bien estructurado y ser fácil de entender.  
 **Validación de Datos:** Se deben evitar entradas vacías y prevenir SQL Injection.  
 **Navegación Correcta:** Las redirecciones entre páginas deben funcionar adecuadamente.  


---

# **Rúbrica de Evaluación – Práctica: Gestión de una Biblioteca Online**  

| **Criterio** | **0 puntos (Deficiente)** | **1 punto (Aceptable)** | **2 puntos (Óptimo)** |
|-------------|-------------------------|-------------------------|------------------------|
| **1. Creación de la Base de Datos** | No se creó la base de datos o tiene errores graves en la estructura. | La base de datos está creada, pero presenta errores en las relaciones o falta algún campo importante. | La base de datos está bien estructurada, con relaciones correctas y datos de prueba insertados. |
| **2. Registro de Usuarios** | No se implementa el formulario de registro o tiene errores que impiden su uso. | El registro de usuarios funciona, pero no almacena la contraseña de forma segura o tiene validaciones deficientes. | El registro funciona correctamente, almacena la contraseña cifrada y valida los datos de entrada. |
| **3. Inicio de Sesión** | No se implementa o el usuario no puede autenticarse correctamente. | Permite iniciar sesión, pero presenta fallos en validaciones o sesiones. | El inicio de sesión funciona correctamente, valida credenciales y maneja sesiones de manera segura. |
| **4. Listado de Libros** | No se muestra el listado de libros o la consulta tiene errores. | Se muestra el listado, pero hay errores en la visualización o en la consulta a la base de datos. | El listado de libros se muestra correctamente con información clara y bien organizada. |
| **5. Solicitud de Préstamo** | No se implementa el préstamo de libros o no se almacena en la base de datos. | Se permite solicitar préstamos, pero presenta errores en la validación o en la base de datos. | El sistema de préstamos funciona correctamente y almacena los datos de forma adecuada. |
| **6. Seguridad en el Manejo de Datos** | No se implementan medidas de seguridad, permitiendo SQL Injection o contraseñas en texto plano. | Se implementan algunas medidas de seguridad, pero hay fallos que pueden comprometer la integridad de los datos. | Se implementan correctamente medidas de seguridad como hashing de contraseñas y consultas seguras. |
| **7. Restricción de Acceso a Páginas Protegidas** | Cualquier usuario puede acceder a páginas sin iniciar sesión. | Se restringe el acceso, pero hay fallos que permiten el acceso indebido. | Las páginas protegidas requieren sesión activa y redirigen correctamente si el usuario no está autenticado. |
| **8. Cierre de Sesión** | No se implementa el cierre de sesión o no elimina correctamente los datos de sesión. | Permite cerrar sesión, pero presenta fallos en la redirección o manejo de sesiones. | El cierre de sesión funciona correctamente y redirige al usuario adecuadamente. |
| **9. Validación de Datos en Formularios** | No se validan los datos de los formularios, permitiendo entradas vacías o incorrectas. | Se validan los datos, pero faltan algunos controles importantes. | Se validan correctamente todos los datos de los formularios para evitar errores y datos inválidos. |

### **Cálculo de la Nota Final**  
- **Puntuación máxima:** 18 puntos.  
- **Conversión a escala de 10:** `(Puntos obtenidos / 18) * 10`.  

---
