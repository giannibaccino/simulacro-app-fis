# Informe Académico 1

## Repositorio Git

Se mantendrá la estructura de directorios inicialmente propuesta para el proyecto, garantizando un orden coherente entre los diferentes componentes del sistema.
De momento, solo se agregó la carpeta **docs/assets** que tendrá todas las imágenes y recursos utilizados en la documentación

El repositorio contará con una rama principal (**main**) que contendrá la última versión funcional y estable del código.
A partir de esta, se utiliza una rama **dev**, donde se integran los cambios provenientes de las diferentes ramas de desarrollo antes de pasar a producción.
Además, se dispone de una rama **qa**, destinada a la validación y pruebas de calidad del código antes de su fusión final con **main** .

Para cada nueva funcionalidad o tarea, se crea una rama específica desde **dev** utilizando la siguiente nomenclatura:

docs-<editor> → para modificar documentación

feature/<nombre-feature> → para nuevas funcionalidades

tarea/<nombre-tarea> → para tareas específicas

fix/<nombre-fix> → para correcciones de errores

Una vez que los cambios son revisados y aprobados, se integran en **dev**, posteriormente se testean en **qa**, y finalmente se fusionan en **main**.

Los mensajes de commit se redactan en español, siguiendo las convenciones de Conventional Commits, con la siguiente estructura:

```
<tipo>[ámbito opcional]: <descripción>

[cuerpo opcional]

[nota de pie opcional]
```

Ejemplos de tipos comunes: _feat, fix, docs, style, refactor, test, chore_.

Durante esta primera fase, enfocada principalmente en la documentación y análisis preliminar, el equipo decidió trabajar de forma colaborativa en Notion, por resultar una herramienta más práctica para esta etapa.
Por este motivo, en el repositorio se registra un único commit inicial, correspondiente a la carga del material base, mientras que la mayor parte del trabajo se desarrolló en dicha plataforma.

---

## Investigación

Los métodos de investigación utilizados fueron encuestas, entrevistas, análisis documental y la elaboración de User Persona.

Las encuestas se realizaron a personas adultas de distintos rangos de edad. Los resultados dejaron en evidencia una clara falta de conocimiento sobre los conceptos vinculados a la inversión, con un promedio de comprensión medio-bajo. Esta carencia de información es uno de los principales factores que impide a los usuarios utilizar aplicaciones de inversión o incluso animarse a invertir. Por ello, consideramos importante incluir una sección de tutoriales y aprendizaje dentro de la aplicación, la cual contribuiría también a aumentar la confianza de los usuarios. Un usuario informado y familiarizado con las funcionalidades de la plataforma tendrá una mayor capacidad de toma de decisiones.

Asimismo, se observó que no existen aplicaciones locales similares, ya que los participantes con experiencia previa habían utilizado plataformas extranjeras. Esto representa una oportunidad diferencial para nuestro proyecto. Además, los resultados mostraron un mayor interés por instrumentos como bonos y acciones, lo que permitiría adaptar la oferta al mercado local y fomentar una mayor actividad dentro de la aplicación.

En las entrevistas, surgieron hallazgos consistentes con los resultados de las encuestas. Los entrevistados expresaron desconfianza y temor al riesgo, lo que refuerza la necesidad de una interfaz amigable y un proceso inicial sencillo. También destacaron la importancia de contar con información clara y fácilmente accesible, por lo que se propone implementar dashboards intuitivos que presenten los históricos y los datos más relevantes de cada activo. Finalmente, la seguridad fue un punto recurrente: los usuarios más experimentados destacaron que la protección de datos y transacciones es un factor decisivo al elegir una plataforma. En consecuencia, se deberán incorporar medidas robustas de seguridad tanto en el registro como en las operaciones.

El análisis documental y la revisión de aplicaciones similares en el mercado permitieron identificar buenas prácticas y funcionalidades clave, como una interfaz limpia, accesible y un posible simulador de inversiones. Esta herramienta permitiría a los usuarios principiantes experimentar con una billetera ficticia antes de realizar operaciones reales. La transparencia también se posiciona como un valor central, por lo que se propone cumplir y comunicar el cumplimiento de normas ISO para generar confianza y credibilidad.

Con base en los hallazgos obtenidos, se definieron los siguientes User Persona:

1. ![User Persona 1](./assets/userPersona1.png)
2. ![User Persona 2](./assets/userPersona2.png)

---

## RF & RNF (Requisitos Funcionales y No Funcionales)

### Requerimientos Funcionales

| Identificador | Requerimiento                                                  | Descripción                                                                                                                                                                                | Prioridad   |
| ------------- | -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------- |
| RF 001        | Login / Sign in                                                | El sistema debe permitir que se registren y logueen usuarios                                                                                                                               | Must Have   |
| RF 002        | Recuperación de contraseña                                     | El sistema debe permitir al usuario recuperar la contraseña olvidada mediante email o SMS.                                                                                                 | Must Have   |
| RF 003        | Mostrar listado de mercados                                    | El sistema debe listar todos los activos disponibles para su compra venta, con los detalles de cada activo                                                                                 | Must Have   |
| RF 004        | Compra y Venta de Activos                                      | El sistema debe permitir al usuario comprar y vender los activos al precio listado.                                                                                                        | Must Have   |
| RF 005        | Historial de transacciones                                     | El sistema debe permitir al usuario ver todo el historial de las operaciones que realizo (compra, venta, retiro o deposito)                                                                | Must Have   |
| RF 006        | Dashboard de monitoreo                                         | El sistema debe tener una sección para que el usuario pueda ver las operaciones en vivo de los activos que elija del mercado                                                               | Must Have   |
| RF 007        | Datos de billetera                                             | El sistema debe permitir al usuario ver sus estados de cuenta, saldos y activos en su billetera                                                                                            | Must Have   |
| RF 008        | Transferencia de dinero                                        | El sistema debe permitir la transferencia de dinero de usuario a cuentas de banco                                                                                                          | Must Have   |
| RF 009        | Seteo de límites de inversión (Stop Loss / Take Profit)        | El sistema debe permitir al usuario definir límites automáticos para cada inversión (stop loss y take profit) con el fin de controlar riesgos o asegurar ganancias.                        | Should Have |
| RF 010        | Notificaciones                                                 | El sistema debe notificar al usuario sobre las operaciones realizadas con éxito o en caso de error                                                                                         | Should Have |
| RF 011        | Borrar cuenta                                                  | El sistema debe permitir al usuario borrar su cuenta, sin perder su billetera                                                                                                              | Could Have  |
| RF 012        | Simulacion de inversiones                                      | El sistema debe proveer un sandbox para probar y aprender a utilizar el app o invertir, con dinero virtual y ficticio.                                                                     | Could Have  |
| RF 013        | Verificación de autenticidad                                   | Antes de toda operación el sistema debe pedir al usuario que se verifique su identidad                                                                                                     | Could Have  |
| RF 014        | Integración con SSO                                            | El sistema debe implementar SSO para poder integras todas las opciones de login para el usuario                                                                                            | Could Have  |
| RF 015        | Integración con billeteras virtuales                           | El sistema debe permitir la integración de billetera virtuales en caso de uso de cripto monedas como activo                                                                                | Could Have  |
| RF 016        | Configuración de perfil de usuario (Preferencias de inversión) | El sistema debe permitir al usuario establecer su perfil de inversión (por ejemplo, conservador, moderado o agresivo) y personalizar preferencias como tipos de activos o nivel de riesgo. | Could Have  |
| RF 017        | Alertas de Inversion                                           | El sistema debe proveer de alertas con sugerencias de potenciales inversiones segun el perfil del usuario, de manera diaria o semanal.                                                     | Could Have  |
| RF 018        | Actualización de contraseña                                    | El sistema debe permitir al usuario actualizar su contraseña desde el perfil.                                                                                                              | Could Have  |
| RF 019        | Actualización de datos de usuario                              | El sistema debe permitir al usuario actualizar sus datos personales (nombre, email, teléfono).                                                                                             | Could Have  |

---

### Requerimientos No Funcionales

| Identificador | Requerimiento No Funcional          | Descripción                                                                                                                                                                              | Prioridad   |
| ------------- | ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| RNF 001       | Tiempo de login                     | La plataforma debe autenticar usuarios y cargar el inicio de sesión en menos de 3 segundos bajo carga normal.                                                                            | Must Have   |
| RNF 002       | Seguridad de datos en login         | Credenciales y datos sensibles deben cifrarse en tránsito (TLS 1.2+) y en reposo (AES-256).                                                                                              | Must Have   |
| RNF 003       | Seguridad en gestion de contraseñas | Todos los procesos de registro, recuperación y actualización de contraseña deben usar cifrado seguro (TLS 1.2+), con hashing de contraseñas y protección contra ataques de fuerza bruta. | Must Have   |
| RNF 004       | Latencia listado de activos         | La lista de activos y sus detalles deben cargarse en menos de 2 segundos.                                                                                                                | Must Have   |
| RNF 005       | Integridad listado de activos       | Los datos mostrados deben reflejar correctamente los valores actuales del mercado sin inconsistencias.                                                                                   | Must Have   |
| RNF 006       | Latencia compra/venta               | Las operaciones de compra o venta deben completarse y reflejarse en la billetera en menos de 5 segundos.                                                                                 | Must Have   |
| RNF 007       | Integridad compra/venta             | Las transacciones deben ser atómicas, sin pérdida ni inconsistencias de saldo o activos.                                                                                                 | Must Have   |
| RNF 008       | Trazabilidad de operaciones         | Registrar cada operación con fecha, hora, usuario, tipo de operación, activo y monto.                                                                                                    | Must Have   |
| RNF 010       | Latencia dashboard                  | La actualización de precios y datos en vivo debe ocurrir en menos de 2 segundos.                                                                                                         | Must Have   |
| RNF 011       | Usabilidad dashboard                | Interfaz clara, visualización de datos fácil de interpretar y responsive para móviles, tabletas y desktop.                                                                               | Must Have   |
| RNF 012       | Integridad billetera                | Todos los saldos y movimientos deben reflejarse correctamente y en tiempo real.                                                                                                          | Must Have   |
| RNF 013       | Seguridad billetera                 | Protección de los datos de billetera mediante cifrado y control de acceso interno.                                                                                                       | Must Have   |
| RNF 014       | Latencia transferencias             | Las transferencias a cuentas bancarias deben procesarse en menos de 10 segundos.                                                                                                         | Must Have   |
| RNF 017       | Rendimiento sandbox                 | Las operaciones en el sandbox deben reflejar los cambios en pantalla en menos de 2 segundos.                                                                                             | Could Have  |
| RNF 018       | Seguridad verificación identidad    | La verificación de identidad debe procesarse sin exponer información sensible, cumpliendo KYC.                                                                                           | Could Have  |
| RNF 019       | Integridad límites inversión        | Los límites de inversión configurados deben aplicarse correctamente sin errores de cálculo.                                                                                              | Should Have |
| RNF 020       | Latencia alertas de inversión       | Las alertas deben mostrarse en menos de 3 segundos desde que se cumple la condición.                                                                                                     | Could Have  |
| RNF 021       | Capacidad concurrente               | Soportar al menos 1000 usuarios concurrentes activos manteniendo los tiempos de respuesta definidos.                                                                                     | Should Have |

## User Stories & Use Cases

## Use Cases

| 1                     | Registro de usuario                                                             |                                                    |
| --------------------- | ------------------------------------------------------------------------------- | -------------------------------------------------- |
| **Descripción**       | Permite que un nuevo usuario se registre en la aplicación con sus datos básicos |                                                    |
| **Actores**           | Usuario                                                                         |                                                    |
| **Precondiciones**    | Usuario no registrado                                                           |                                                    |
| **Post Condiciones**  | Usuario registrado y cuenta activada                                            |                                                    |
| **Curso normal**      | **Acción (actor)**                                                              | **Reacción (sistema)**                             |
|                       | 1. Accede a "Registrar"                                                         | 2. Muestra formulario de registro                  |
|                       | 3. Completa datos y envía                                                       | 4. Valida datos y crea cuenta                      |
|                       | 5. Envía email de verificación                                                  | 6. Confirma registro exitoso                       |
| **Curso alternativo** | 3.1 Email ya registrado                                                         | 4.1 Muestra mensaje de error y solicita otro email |

---

| 2                     | Ingresar al sistema (Login)                            |                                                  |
| --------------------- | ------------------------------------------------------ | ------------------------------------------------ |
| **Descripción**       | Permite al usuario iniciar sesión con sus credenciales |                                                  |
| **Actores**           | Usuario                                                |                                                  |
| **Precondiciones**    | Usuario registrado y cuenta activada                   |                                                  |
| **Post Condiciones**  | Usuario autenticado y sesión iniciada                  |                                                  |
| **Curso normal**      | **Acción (actor)**                                     | **Reacción (sistema)**                           |
|                       | 1. Ingresa email y contraseña                          | 2. Valida credenciales                           |
|                       | 3. Solicita inicio de sesión                           | 4. Inicia sesión y muestra pantalla principal    |
| **Curso alternativo** | 1.1 Credenciales incorrectas                           | 2.1 Muestra mensaje de error y permite reintento |

---

| 3                     | Recuperación de contraseña                          |                                                |
| --------------------- | --------------------------------------------------- | ---------------------------------------------- |
| **Descripción**       | Permite al usuario recuperar la contraseña olvidada |                                                |
| **Actores**           | Usuario                                             |                                                |
| **Precondiciones**    | Usuario registrado                                  |                                                |
| **Post Condiciones**  | Usuario con nueva contraseña válida                 |                                                |
| **Curso normal**      | **Acción (actor)**                                  | **Reacción (sistema)**                         |
|                       | 1. Solicita recuperación de contraseña              | 2. Muestra formulario o enlace de recuperación |
|                       | 3. Ingresa email o teléfono                         | 4. Envía enlace o código temporal              |
|                       | 5. Ingresa nueva contraseña                         | 6. Valida y actualiza contraseña               |
| **Curso alternativo** | 3.1 Email no registrado                             | 4.1 Muestra mensaje de error                   |

---

| 4                     | Mostrar listado de mercados                                             |                                                      |
| --------------------- | ----------------------------------------------------------------------- | ---------------------------------------------------- |
| **Descripción**       | Permite al usuario visualizar todos los activos disponibles para operar |                                                      |
| **Actores**           | Usuario                                                                 |                                                      |
| **Precondiciones**    | Usuario autenticado                                                     |                                                      |
| **Post Condiciones**  | Se muestra listado actualizado de activos                               |                                                      |
| **Curso normal**      | **Acción (actor)**                                                      | **Reacción (sistema)**                               |
|                       | 1. Accede a "Mercados"                                                  | 2. Muestra listado de activos con información básica |
|                       | 3. Filtra o busca un activo                                             | 4. Muestra resultados filtrados                      |
|                       | 5. Selecciona un activo                                                 | 6. Muestra detalle con precio, variación y opciones  |
| **Curso alternativo** | 3.1 No hay activos disponibles                                          | 4.1 Muestra mensaje “Activo no encontrado”           |

---

| 5                     | Compra y venta de activos                                                |                                                  |
| --------------------- | ------------------------------------------------------------------------ | ------------------------------------------------ |
| **Descripción**       | Permite al usuario comprar o vender activos según disponibilidad y saldo |                                                  |
| **Actores**           | Usuario                                                                  |                                                  |
| **Precondiciones**    | Usuario autenticado, saldo disponible                                    |                                                  |
| **Post Condiciones**  | Operación realizada y saldos actualizados                                |                                                  |
| **Curso normal**      | **Acción (actor)**                                                       | **Reacción (sistema)**                           |
|                       | 1. Selecciona activo                                                     | 2. Muestra opciones de compra/venta              |
|                       | 3. Ingresa cantidad y confirma                                           | 4. Valida saldo y precio                         |
|                       | 5. Confirma operación                                                    | 6. Ejecuta transacción y actualiza saldo         |
| **Curso alternativo** | 3.1 Fondos insuficientes                                                 | 4.1 Muestra mensaje de error y cancela operación |

---

| 6                     | Historial de transacciones                                      |                                                        |
| --------------------- | --------------------------------------------------------------- | ------------------------------------------------------ |
| **Descripción**       | Permite consultar operaciones pasadas realizadas por el usuario |                                                        |
| **Actores**           | Usuario                                                         |                                                        |
| **Precondiciones**    | Usuario autenticado                                             |                                                        |
| **Post Condiciones**  | Se muestra listado de todas las transacciones                   |                                                        |
| **Curso normal**      | **Acción (actor)**                                              | **Reacción (sistema)**                                 |
|                       | 1. Accede a "Historial"                                         | 2. Recupera lista de operaciones                       |
|                       | 3. Filtra por tipo o fecha                                      | 4. Actualiza resultados según filtro                   |
| **Curso alternativo** | 1.1 No hay operaciones registradas                              | 2.1 Muestra mensaje “No hay transacciones disponibles” |

---

| 7                     | Dashboard de monitoreo                                             |                                                         |
| --------------------- | ------------------------------------------------------------------ | ------------------------------------------------------- |
| **Descripción**       | Permite al usuario visualizar en tiempo real los activos que sigue |                                                         |
| **Actores**           | Usuario                                                            |                                                         |
| **Precondiciones**    | Usuario autenticado, activos seleccionados                         |                                                         |
| **Post Condiciones**  | Muestra datos actualizados y gráficos en tiempo real               |                                                         |
| **Curso normal**      | **Acción (actor)**                                                 | **Reacción (sistema)**                                  |
|                       | 1. Accede al dashboard                                             | 2. Carga datos de activos seleccionados                 |
|                       | 3. Interactúa con gráficos                                         | 4. Actualiza información en tiempo real                 |
| **Curso alternativo** | 2.1 Error de conexión                                              | 3.1 Muestra último valor disponible y alerta al usuario |

---

| 8                     | Datos de billetera                                                   |                                                   |
| --------------------- | -------------------------------------------------------------------- | ------------------------------------------------- |
| **Descripción**       | Permite ver saldo, activos y movimientos de la billetera del usuario |                                                   |
| **Actores**           | Usuario                                                              |                                                   |
| **Precondiciones**    | Usuario autenticado                                                  |                                                   |
| **Post Condiciones**  | Muestra información actualizada de la billetera                      |                                                   |
| **Curso normal**      | **Acción (actor)**                                                   | **Reacción (sistema)**                            |
|                       | 1. Accede a "Mi billetera"                                           | 2. Muestra saldo y activos                        |
|                       | 3. Consulta detalle de movimientos                                   | 4. Muestra historial reciente                     |
| **Curso alternativo** | 3.1 No hay movimientos                                               | 4.1 Muestra mensaje “Sin movimientos disponibles” |

---

| 9                     | Transferencia de dinero                     |                                               |
| --------------------- | ------------------------------------------- | --------------------------------------------- |
| **Descripción**       | Permite enviar dinero a otra cuenta o banco |                                               |
| **Actores**           | Usuario emisor, Usuario receptor            |                                               |
| **Precondiciones**    | Usuarios registrados y autenticados         |                                               |
| **Post Condiciones**  | Fondos transferidos correctamente           |                                               |
| **Curso normal**      | **Acción (actor)**                          | **Reacción (sistema)**                        |
|                       | 1. Accede a “Transferir”                    | 2. Muestra formulario de transferencia        |
|                       | 3. Ingresa destinatario y monto             | 4. Valida datos y fondos                      |
|                       | 5. Confirma operación                       | 6. Ejecuta transferencia y notifica resultado |
| **Curso alternativo** | 3.1 Fondos insuficientes                    | 4.1 Cancela operación y muestra error         |

---

| 10                    | Seteo de límites de inversión (Stop Loss / Take Profit) |                                                 |
| --------------------- | ------------------------------------------------------- | ----------------------------------------------- |
| **Descripción**       | Permite definir límites automáticos de compra/venta     |                                                 |
| **Actores**           | Usuario                                                 |                                                 |
| **Precondiciones**    | Usuario autenticado                                     |                                                 |
| **Post Condiciones**  | Límites configurados y operando                         |                                                 |
| **Curso normal**      | **Acción (actor)**                                      | **Reacción (sistema)**                          |
|                       | 1. Accede a configuración de límites                    | 2. Muestra formulario para cada activo          |
|                       | 3. Ingresa valores de stop loss y take profit           | 4. Guarda límites y activa monitor              |
|                       | 5. Llega al límite                                      | 6. Ejecuta operación automáticamente y notifica |
| **Curso alternativo** | 3.1 Valores inválidos                                   | 4.1 Muestra error y solicita reingreso          |

---

| 11                    | Notificaciones                                               |                                                 |
| --------------------- | ------------------------------------------------------------ | ----------------------------------------------- |
| **Descripción**       | Permite recibir alertas de operaciones y eventos importantes |                                                 |
| **Actores**           | Usuario                                                      |                                                 |
| **Precondiciones**    | Usuario autenticado                                          |                                                 |
| **Post Condiciones**  | Usuario recibe notificaciones en tiempo real                 |                                                 |
| **Curso normal**      | **Acción (actor)**                                           | **Reacción (sistema)**                          |
|                       | 1. Realiza operación o evento relevante                      | 2. Envía notificación inmediata                 |
|                       | 3. Consulta historial de notificaciones                      | 4. Muestra listado de alertas previas           |
| **Curso alternativo** | 2.1 Error de entrega                                         | 3.1 Almacena notificación pendiente y reintenta |

---

| 12                    | Borrar cuenta                                                   |                               |
| --------------------- | --------------------------------------------------------------- | ----------------------------- |
| **Descripción**       | Permite eliminar la cuenta del usuario sin afectar su billetera |                               |
| **Actores**           | Usuario                                                         |                               |
| **Precondiciones**    | Usuario autenticado                                             |                               |
| **Post Condiciones**  | Cuenta eliminada y billetera preservada                         |                               |
| **Curso normal**      | **Acción (actor)**                                              | **Reacción (sistema)**        |
|                       | 1. Accede a "Configuración > Eliminar cuenta"                   | 2. Solicita confirmación      |
|                       | 3. Confirma eliminación                                         | 4. Borra cuenta y notifica    |
| **Curso alternativo** | 3.1 Cancela proceso                                             | 4.1 No realiza ninguna acción |

---

| 13                    | Simulación de inversiones                                |                                                 |
| --------------------- | -------------------------------------------------------- | ----------------------------------------------- |
| **Descripción**       | Permite practicar con dinero virtual sin riesgo          |                                                 |
| **Actores**           | Usuario                                                  |                                                 |
| **Precondiciones**    | Usuario autenticado                                      |                                                 |
| **Post Condiciones**  | Entorno de simulación activo y saldo ficticio disponible |                                                 |
| **Curso normal**      | **Acción (actor)**                                       | **Reacción (sistema)**                          |
|                       | 1. Accede a modo simulación                              | 2. Carga saldo virtual inicial                  |
|                       | 3. Realiza operaciones                                   | 4. Simula resultados como en real               |
| **Curso alternativo** | 2.1 Error de carga                                       | 3.1 Muestra mensaje de error y sugiere reinicio |

---

| 14                    | Verificación de autenticidad                         |                                                    |
| --------------------- | ---------------------------------------------------- | -------------------------------------------------- |
| **Descripción**       | Solicita verificación antes de operaciones sensibles |                                                    |
| **Actores**           | Usuario                                              |                                                    |
| **Precondiciones**    | Usuario autenticado                                  |                                                    |
| **Post Condiciones**  | Operación ejecutada solo si autenticación exitosa    |                                                    |
| **Curso normal**      | **Acción (actor)**                                   | **Reacción (sistema)**                             |
|                       | 1. Inicia operación sensible                         | 2. Solicita verificación (PIN, código o biometría) |
|                       | 3. Ingresa método de verificación                    | 4. Valida autenticidad y permite operación         |
| **Curso alternativo** | 3.1 Verificación fallida                             | 4.1 Cancela operación y notifica intento fallido   |

---

| 15                    | Integración con SSO                                              |                                      |
| --------------------- | ---------------------------------------------------------------- | ------------------------------------ |
| **Descripción**       | Permite iniciar sesión mediante cuentas externas (Google, Apple) |                                      |
| **Actores**           | Usuario                                                          |                                      |
| **Precondiciones**    | Usuario con cuenta externa válida                                |                                      |
| **Post Condiciones**  | Usuario autenticado sin usar credenciales locales                |                                      |
| **Curso normal**      | **Acción (actor)**                                               | **Reacción (sistema)**               |
|                       | 1. Click en "Iniciar sesión con SSO"                             | 2. Redirige a proveedor SSO          |
|                       | 3. Autoriza acceso                                               | 4. Valida y vincula cuenta           |
| **Curso alternativo** | 3.1 Usuario no autoriza                                          | 4.1 Cancela inicio y muestra mensaje |

---

| 16                    | Integración con billeteras virtuales                  |                                               |
| --------------------- | ----------------------------------------------------- | --------------------------------------------- |
| **Descripción**       | Permite vincular billeteras externas de criptomonedas |                                               |
| **Actores**           | Usuario                                               |                                               |
| **Precondiciones**    | Usuario autenticado, billetera compatible             |                                               |
| **Post Condiciones**  | Billetera vinculada y sincronizada                    |                                               |
| **Curso normal**      | **Acción (actor)**                                    | **Reacción (sistema)**                        |
|                       | 1. Accede a “Integraciones”                           | 2. Muestra opciones de billeteras disponibles |
|                       | 3. Selecciona billetera y autoriza                    | 4. Sincroniza saldos y movimientos            |
| **Curso alternativo** | 3.1 Error de autenticación                            | 4.1 Muestra mensaje de fallo en conexión      |

---

| 17                    | Configuración de perfil de usuario (Preferencias de inversión) |                                                   |
| --------------------- | -------------------------------------------------------------- | ------------------------------------------------- |
| **Descripción**       | Permite definir perfil de riesgo y preferencias de inversión   |                                                   |
| **Actores**           | Usuario                                                        |                                                   |
| **Precondiciones**    | Usuario autenticado                                            |                                                   |
| **Post Condiciones**  | Perfil de inversión configurado y aplicado                     |                                                   |
| **Curso normal**      | **Acción (actor)**                                             | **Reacción (sistema)**                            |
|                       | 1. Accede a configuración de perfil                            | 2. Muestra opciones de perfil y preferencias      |
|                       | 3. Selecciona opciones                                         | 4. Guarda preferencias y aplica a recomendaciones |
| **Curso alternativo** | 3.1 Valores inválidos                                          | 4.1 Muestra error y solicita corrección           |

---

| 18                    | Alertas de inversión                                             |                                             |
| --------------------- | ---------------------------------------------------------------- | ------------------------------------------- |
| **Descripción**       | Permite recibir alertas personalizadas según perfil de inversión |                                             |
| **Actores**           | Usuario                                                          |                                             |
| **Precondiciones**    | Usuario autenticado, perfil definido                             |                                             |
| **Post Condiciones**  | Alertas configuradas y enviadas según preferencias               |                                             |
| **Curso normal**      | **Acción (actor)**                                               | **Reacción (sistema)**                      |
|                       | 1. Sistema analiza mercado según perfil                          | 2. Genera alertas relevantes                |
|                       | 3. Usuario recibe alertas                                        | 4. Permite aceptar o ignorar oportunidades  |
| **Curso alternativo** | 2.1 Error en generación de alertas                               | 3.1 Envía notificación de error y reintenta |

## User stories

### **MUST HAVE**

### **US-001 - Autenticación y acceso seguro**

Como usuario, quiero poder registrarme, iniciar sesión o recuperar mi contraseña, para acceder de forma segura a la aplicación.

**Criterios de aceptación:**

- Crear cuenta con email, contraseña y datos personales válidos.
- Enviar email de verificación o notificar en caso de error.
- Recuperacion de cuenta mediante email.
- Registro seguro: cifrado de contraseñas (hash + salt) y protección contra duplicados.
- Operación completada en menos de 3 segundos.

---

### **US-002 – Gestión de cuenta de usuario**

Como usuario, quiero editar mi información personal o eliminar mi cuenta, para mantener mis datos actualizados o cerrar mi sesion.

**Criterios de aceptación:**

- Edición de nombre, email o imagen.
- Confirmación doble antes de eliminar cuenta.
- Persistencia de cambios.
- Notificacion de confirmación.

---

### **US-003 – Mostrar listado de mercados**

Como usuario, quiero poder ver un listado con todos los activos disponibles para compra o venta, para decidir en cuáles invertir.

**Criterios de aceptación:**

- Mostrar nombre, precio actual, variación y tipo de activo.
- Actualización en intervalos definidos.
- Acceso al detalle de cada activo.
- Filtros y orden por rentabilidad o tipo.
- Carga en menos de 2 segundos.

---

### **US-004 – Compra y venta de activos**

Como usuario, quiero poder comprar y vender activos al precio listado, para gestionar mis inversiones dentro del sistema.

**Criterios de aceptación:**

- Validación de saldo o disponibilidad de activos.
- Confirmación de transacción
- Actualización de saldos/activos.
- Operaciones reflejadas en billetera en menos de 5 segundos.
- Notificacion de exito o error.

---

### **US-005 – Historial de transacciones**

Como usuario, quiero poder consultar mi historial completo de transacciones, para revisar mis operaciones anteriores.

**Criterios de aceptación:**

- Listado de todas las operaciones realizadas (compra, venta, retiro, depósito).
- Mostrar tipo, fecha, monto, activo y estado.
- Filtro o búsqueda por tipo o fecha.
- Registro preciso de cada operación.

---

### **US-006 – Gestion de billetera**

Como usuario, quiero ver mi saldo, movimientos y transferir dinero, para controlar mis fondos.

**Criterios de aceptación:**

- Mostrar saldo total disponible.
- Listar activos con su valor actual.
- Transferencias internas o bancarias.
- Notifiacion de transferencia exitosa o error
- Incluir últimos movimientos.
- Transacciones protegidas.

---

### **US-007 - Seguridad y verificación**

Como usuario, quiero validar mi identidad antes de ciertas acciones, para garantizar la seguridad de mis fondos.

- Solicitud de verificacion en operaciones sensibles
- Bloqueo tras intentos fallidos
- Cumplimiento de normas KYC
- Registro de historial (auditoria)

---

### **US-008 – Dashboard de monitoreo**

Como usuario, quiero ver un panel donde pueda monitorear en tiempo real los activos que sigo, para tomar decisiones informadas.

**Criterios de aceptación:**

- Precios actualizados y variaciones.
- Gráficos con indicadores visuales.
- Actualización automática de información.
- Datos en vivo en menos de 2 segundos.
- Interfaz clara, interpretativa y responsive.

---

### **SHOULD HAVE**

### **US-009 – Notificaciones**

Como usuario, quiero recibir notificaciones sobre mis operaciones para mantenerme informado en tiempo real.

**Criterios de aceptación:**

- Notificaciones en tiempo real.
- Historial de notificaciones disponible.
- Notificaciones claras, breves y precisas.
- Posibilidad de silenciar o activar.
- Entrega en menos de 3 segundos desde el evento.

---

### **US-010 – Simulación de inversiones**

Como usuario, quiero acceder a un modo de simulación con dinero virtual para practicar inversiones sin riesgo.

**Criterios de aceptación:**

- Entorno de simulación con misma logica que el real.
- Billetera ficticia para practicar.
- Reinicio de simulación disponible en cualquier momento.
- Indicador de modo "Demo"

---

### **COULD HAVE**

### **US-011 – Configuración de perfil de inversión**

Como usuario, quiero configurar mi perfil de inversión y preferencias para recibir recomendaciones acordes a mi nivel de riesgo.

**Criterios de aceptación:**

- Definición de perfil: conservador, moderado o agresivo.
- Selección de sectores o activos de interés.
- Preferencias influyen en alertas y recomendaciones.
- Posibilidad de modificar perfil en cualquier momento.

---

### **US-012 – Integración con billeteras externas**

Como usuario, quiero vincular mi billetera virtual de criptomonedas con la aplicación para operar con activos digitales.

**Criterios de aceptación:**

- Vinculación y desvinculación de cuentas.
- Visualización de saldo y movimientos.
- Conexion y operaciones seguras.
- Notificación si la vinculación falla.

---

## Modelo de Dominio

Se creo un modelo entidad-relación preliminar utilizando la herramienta Whimsical, con el objetivo de representar de forma visual y organizada las principales entidades del sistema y sus relaciones.

![Imagen de modelo](./assets/Modelo%20Conceptual.png)

---

## Verificación y Validación

- **Verificación:** describir cómo comprobaron que los RF/RNF cumplen con lo especificado (revisiones, checklist, trazabilidad).
- **Validación:** actividades con usuarios (feedback de encuestas, entrevistas, prototipos).
- Mostrar resultados obtenidos y cómo influyeron en futuras mejoras al proyecto.

# Verificación de Requerimientos - Informe

## Checklist para Verificación

### 1. Compleción

- ¿Se encuentran los requerimientos correctamente priorizados?
- ¿Son todas las clases de usuarios identificados y sus características descriptas?
- ¿Respeta la especificación la estructura y apartados del estándar?
- ¿Se identifican y describen las dependencias con otros sistemas?
- ¿Están todas las características de calidad tenidas en cuenta en la especificación?

### 2. Corrección y Consistencia

- ¿Están los requerimientos escritos en forma consistente y a un nivel de detalle adecuado?
- ¿Existe duplicación de requerimientos o conflicto entre requerimientos?
- ¿Está cada requerimiento dentro del alcance del problema a resolver?
- ¿Evitan los requerimientos incluir aspectos de diseño o implementación de la solución?

### 3. Verificabilidad y No Ambigüedad

- ¿Tiene cada requerimiento una única interpretación?
- ¿Puede ser cada requerimiento verificado por alguna prueba, demostración, revisión o análisis?
- ¿Se utiliza un lenguaje preciso y sin jerga innecesaria?

### 4. Trazabilidad

- ¿Puede cada requerimiento ser identificado correctamente y en forma única?
- ¿Se referencian correctamente los requerimientos entre sí?
- ¿Puede cada requerimiento ser referenciado hasta su origen (alguna necesidad de los stakeholders)?

---

# 📋 Tabla de Validación de Requerimientos

| ID       | Requerimiento                                                  | Origen                                                                                      | Completitud | ¿Priorizado correctamente? | ¿Usuarios identificados? | ¿Dependencias identificadas? | ¿Identificador único? | ¿Origen trazable? | ¿Evita diseño/implementación? | ¿Interpretación única? | ¿Verificable por pruebas? |
| -------- | -------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ----------- | -------------------------- | ------------------------ | ---------------------------- | --------------------- | ----------------- | ----------------------------- | ---------------------- | ------------------------- |
| RF-001   | Login / Sign in                                                | Valentina – acceso seguro y simple; Martín – acceso rápido y controlado                     | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |
| RF-002   | Mostrar listado de mercados                                    | Martín – necesita listado claro para decisión; Valentina – conocer opciones para empezar    | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |
| RF-003   | Compra y Venta de Activos                                      | Ambos – operar activos fácilmente y con seguridad                                           | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |
| RF-003\* | Historial de transacciones                                     | Ambos – seguimiento transparente de operaciones                                             | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |
| RF-004   | Dashboard de monitoreo                                         | Martín – monitoreo rápido y visual; Valentina – confianza con seguimiento en vivo           | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |
| RF-005   | Datos de billetera                                             | Ambos – claridad en saldos y activos                                                        | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |
| RF-006   | Transferencia de dinero                                        | Ambos – facilidad y seguridad en transferencias                                             | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |
| RF-014   | Seteo de límites de inversión (Stop Loss / Take Profit)        | Martín – control de riesgos y aseguramiento de ganancias; Valentina – seguridad al invertir | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |
| RF-007   | Notificaciones                                                 | Martín – alertas resumidas; Valentina – guía y seguridad en proceso                         | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |
| RF-008   | Borrar cuenta                                                  | Ambos – opción para gestionar cuenta sin perder activos                                     | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |
| RF-009   | Simulación de inversiones                                      | Valentina – aprendizaje sin riesgos; Martín – probar estrategias                            | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |
| RF-010   | Verificación de autenticidad                                   | Ambos – seguridad adicional para confianza                                                  | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |
| RF-011   | Integración con SSO                                            | Martín – integración con ecosistemas; Valentina – acceso sencillo                           | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |
| RF-012   | Integración con billeteras virtuales                           | Martín – uso de billetera cripto existente; Valentina – explorar nuevas opciones seguras    | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |
| RF-013   | Configuración de perfil de usuario (Preferencias de inversión) | Martín – personalización y ahorro de tiempo; Valentina – guía ajustada a su nivel           | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |
| RF-014\* | Alertas de Inversion                                           | Martín – recibir sugerencias adaptadas; Valentina – aprendizaje con alertas útiles          | Sí          | Sí                         | Sí                       | Sí                           | Sí                    | Sí                | Sí                            | Sí                     | Sí                        |

---

## Descripción del Trabajo Individual

| Fecha                | Actividades                                                                       | Participantes             | Horas Invertidas |
| -------------------- | --------------------------------------------------------------------------------- | ------------------------- | ---------------- |
| Viernes 3 de Octubre | Brainstorming, definición de modelos de investigación y estructura de repositorio | Facundo, Fernando, Gianni | 2                |
| Sábado 4 de Octubre  | Estructura de Notion y modelado de Encuestas                                      | Facundo, Fernando, Gianni | 2                |
| Sábado 4 de Octubre  | Modelo Conceptual                                                                 | Facundo, Fernando, Gianni | 1                |
| Sábado 4 de Octubre  | Creación de Encuestas                                                             | Facundo, Fernando, Gianni | 2                |
| Domingo 5 de Octubre | Brainstorming                                                                     | Facundo, Fernando, Gianni | 1                |
| Domingo 5 de Octubre | Listado de alcance                                                                | Facundo, Fernando, Gianni | 1                |
| Domingo 5 de Octubre | Priorización                                                                      | Facundo, Fernando, Gianni | 1                |
| Domingo 5 de Octubre | User Personas                                                                     | Facundo, Fernando, Gianni | 1                |

---

## Reflexión

- Reflexionar como equipo sobre:

  - Dinámica de trabajo y comunicación.
  - Dificultades y desafíos encontrados.
  - Qué funcionó bien y qué no.
  - Lecciones aprendidas hasta ahora.

- Mantener un tono crítico y constructivo, no sólo descriptivo.
