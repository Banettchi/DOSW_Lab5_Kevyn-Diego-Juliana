# 📄 Planeación del Sistema

## Desglose de trabajo: Épicas, Historias de Usuario y Tareas

La implementación de los requerimientos identificados de Bankify se desglosa de la siguiente manera:

---

### 1. Épica:

| Campo | Descripción |
|------|-------------|
| **ID** | EP-01 |
| **ID Jira** | KAN-14 |
| **Título** | Gestión de Depósitos Bancarios |
| **Descripción** | Bankify necesita esta épica para permitir que los usuarios autenticados realicen depósitos a cuentas bancarias activas de forma segura y controlada. Esta funcionalidad es el núcleo operativo del sistema financiero, ya que habilita el flujo de dinero entre cuentas, garantiza la trazabilidad de las transacciones y valida la integridad de los datos antes de actualizar los saldos. Sin esta épica, el sistema no puede cumplir su propósito principal como plataforma bancaria digital. |
| **Stakeholder** | Cliente (propietario de cuenta) y cualquier usuario autenticado que desee realizar un depósito a una cuenta bancaria registrada en Bankify. |

---

### 2. Historias de usuario:

| Campo | Descripción |
|------|-------------|
| **ID** | HU-01 |
| **ID Jira** | KAN-15 |
| **Título** | Ingresar número de cuenta destino |
| **Descripción** | Como usuario autenticado, quiero ingresar el número de cuenta destino para poder identificar la cuenta bancaria a la que deseo realizar un depósito. |
| **Prioridad** | Alta |
| **Estimación** | 3 puntos de historia |

| Campo | Descripción |
|------|-------------|
| **ID** | HU-02 |
| **ID Jira** | KAN-14 |
| **Título** | Validar existencia y estado de la cuenta destino |
| **Descripción** | Como usuario autenticado, quiero que el sistema valide automáticamente si la cuenta destino existe y está activa para poder continuar con el depósito solo cuando sea seguro hacerlo. |
| **Prioridad** | Alta |
| **Estimación** | 5 puntos de historia |

| Campo | Descripción |
|------|-------------|
| **ID** | HU-03 |
| **ID Jira** | KAN-17 |
| **Título** | Ingresar y validar monto del depósito |
| **Descripción** | Como usuario autenticado, quiero ingresar el monto a depositar y que el sistema lo valide para poder asegurarme de que el valor ingresado es mayor a cero antes de confirmar la operación. |
| **Prioridad** | Alta |
| **Estimación** | 3 puntos de historia |

| Campo | Descripción |
|------|-------------|
| **ID** | HU-04 |
| **ID Jira** | KAN-18 |
| **Título** | Confirmar depósito y actualizar saldo |
| **Descripción** | Como usuario autenticado, quiero confirmar la operación de depósito para poder actualizar el saldo de la cuenta destino y tener un registro de la transacción realizada. |
| **Prioridad** | Media |
| **Estimación** | 8 puntos de historia |

---

### 3. Tareas:

#### HU-01 – Ingresar número de cuenta destino

| Campo | Descripción |
|------|-------------|
| **ID** | TR-01 |
| **ID Jira** | KAN-19 |
| **Título** | Diseñar formulario de ingreso de cuenta destino |
| **ID de la Historia de Uso asociada** | HU-01 |
| **Descripción** | Como desarrollador, quiero diseñar e implementar el campo de texto en la interfaz para que el usuario pueda ingresar el número de cuenta destino de forma clara y accesible. |
| **Tareas requisito** | — |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-02 |
| **ID Jira** | KAN-20 |
| **Título** | Crear endpoint REST para recibir el número de cuenta destino |
| **ID de la Historia de Uso asociada** | HU-01 |
| **Descripción** | Como desarrollador, quiero implementar un endpoint en el backend que reciba el número de cuenta destino enviado desde el frontend para que el sistema pueda procesarlo y pasarlo a la capa de validación. |
| **Tareas requisito** | — |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-03 |
| **ID Jira** | KAN-21 |
| **Título** | Mostrar mensaje de error si el campo está vacío |
| **ID de la Historia de Uso asociada** | HU-01 |
| **Descripción** | Como desarrollador, quiero agregar una validación en el formulario que muestre un mensaje de error cuando el usuario intente continuar sin ingresar el número de cuenta para evitar que se envíe una petición vacía al servidor. |
| **Tareas requisito** | TR-01 |

---

#### HU-02 – Validar existencia y estado de la cuenta destino

| Campo | Descripción |
|------|-------------|
| **ID** | TR-04 |
| **ID Jira** | KAN-22 |
| **Título** | Implementar lógica de consulta y validación de cuenta en el servicio |
| **ID de la Historia de Uso asociada** | HU-02 |
| **Descripción** | Como desarrollador, quiero implementar la lógica de negocio en la capa de servicio para que, al recibir un número de cuenta, consulte la base de datos, verifique si la cuenta existe y si su estado es activo o inactivo, y retorne ese resultado. Esta tarea representa la comunicación con el backend (base de datos): es quien sabe buscar la cuenta y determinar su estado, y le entrega esa información a TR-05 para que pueda responderle al frontend. |
| **Tareas requisito** | — |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-05 |
| **ID Jira** | KAN-23 |
| **Título** | Implementar endpoint REST de validación de cuenta en el controlador |
| **ID de la Historia de Uso asociada** | HU-02 |
| **Descripción** | Como desarrollador, quiero implementar el endpoint REST en la capa del controlador que reciba la petición del frontend con el número de cuenta, llame al servicio (TR-04) para obtener el resultado de la validación, y devuelva la respuesta al frontend indicando si la cuenta es válida o no. Esta tarea representa la comunicación con el frontend: actúa como intermediario entre la interfaz y el servicio, recibe la pregunta del frontend, se la hace a TR-04, y con la respuesta que TR-04 le da, le informa al frontend si puede continuar o no con el depósito. |
| **Tareas requisito** | TR-04 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-06 |
| **ID Jira** | KAN-24 |
| **Título** | Mostrar mensaje de error si la cuenta no es válida |
| **ID de la Historia de Uso asociada** | HU-02 |
| **Descripción** | Como desarrollador, quiero mostrar un mensaje informativo en la interfaz cuando la cuenta no exista o esté inactiva para que el usuario sepa qué ocurrió y pueda corregir el dato ingresado. |
| **Tareas requisito** | TR-05 |

---

#### HU-03 – Ingresar y validar monto del depósito

| Campo | Descripción |
|------|-------------|
| **ID** | TR-07 |
| **ID Jira** | KAN-25 |
| **Título** | Diseñar campo de ingreso del monto |
| **ID de la Historia de Uso asociada** | HU-03 |
| **Descripción** | Como desarrollador, quiero diseñar e implementar el campo numérico en la interfaz para que el usuario pueda ingresar el monto del depósito de forma intuitiva. |
| **Tareas requisito** | TR-02 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-08 |
| **ID Jira** | KAN-26 |
| **Título** | Validar que el monto sea mayor a cero en el frontend |
| **ID de la Historia de Uso asociada** | HU-03 |
| **Descripción** | Como desarrollador, quiero agregar una validación en el formulario que impida continuar si el monto ingresado es igual o menor a cero para evitar errores antes de enviar la solicitud al servidor. |
| **Tareas requisito** | TR-07 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-09 |
| **ID Jira** | KAN-27 |
| **Título** | Validar monto en el backend |
| **ID de la Historia de Uso asociada** | HU-03 |
| **Descripción** | Como desarrollador, quiero implementar la validación del monto en la capa de servicio del backend para garantizar que ningún depósito con monto inválido sea procesado, incluso si se omite la validación del frontend. |
| **Tareas requisito** | TR-04, TR-08 |

---

#### HU-04 – Confirmar depósito y actualizar saldo

| Campo | Descripción |
|------|-------------|
| **ID** | TR-10 |
| **ID Jira** | KAN-28 |
| **Título** | Implementar lógica de actualización de saldo |
| **ID de la Historia de Uso asociada** | HU-04 |
| **Descripción** | Como desarrollador, quiero implementar la lógica que incremente el saldo de la cuenta destino con el monto del depósito de forma atómica para garantizar la consistencia de los datos en la base de datos. |
| **Tareas requisito** | TR-05, TR-09 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-11 |
| **ID Jira** | KAN-29 |
| **Título** | Registrar transacción en el historial |
| **ID de la Historia de Uso asociada** | HU-04 |
| **Descripción** | Como desarrollador, quiero guardar un registro de la transacción (fecha, hora, monto, cuenta destino y usuario que realizó el depósito) en la base de datos para garantizar la trazabilidad de las operaciones. |
| **Tareas requisito** | TR-10 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-12 |
| **ID Jira** | KAN-30 |
| **Título** | Mostrar confirmación del depósito al usuario |
| **ID de la Historia de Uso asociada** | HU-04 |
| **Descripción** | Como desarrollador, quiero mostrar un mensaje de éxito en la interfaz con el resumen del depósito realizado (monto, cuenta destino y fecha) para que el usuario tenga certeza de que la operación fue completada exitosamente. |
| **Tareas requisito** | TR-10, TR-11 |
