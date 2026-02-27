# 📄 Requerimientos del Sistema

## 1. Lista general de requerimientos

El sistema de Bankify tiene los siguientes requerimientos:

### 1.1 Requerimientos funcionales

El sistema de Bankify debe tener la capacidad de:

1. Autenticar usuarios (cliente, asesor, supervisor y gerente financiero) mediante usuario y contraseña.
2. Gestionar clientes (crear, activar, inactivar, actualizar y eliminar) por parte del supervisor.
3. Gestionar cuentas bancarias (crear, activar, inactivar y actualizar) según el rol del usuario.
4. Consultar el saldo de una cuenta bancaria por parte del cliente.
5. Realizar depósitos a una cuenta bancaria por parte del cliente propietario u otro usuario autenticado.
6. Generar reporte tributario en formato PDF por parte del cliente.
7. Generar y enviar reporte tributario en formato JSON a la DIAN por parte del gerente financiero.

### 1.2 Requerimientos no funcionales

El sistema de Bankify debe tener:

1. Seguridad: Las contraseñas deben almacenarse cifradas con hash seguro (bcrypt o similar).
2. Disponibilidad: El sistema debe estar disponible mínimo el 99% del tiempo en horario laboral.
3. Rendimiento: Las consultas de saldo y depósitos deben responder en menos de 2 segundos.
4. Usabilidad: La interfaz debe permitir que un usuario sin conocimientos técnicos opere sin capacitación.
5. Mantenibilidad: El código debe seguir estándares definidos y tener cobertura de pruebas mínima del 70%.

---

## 2. Diagramas de caso de uso

### 2.1 Requerimiento Funcional 1

| Campo | Descripción                                                                                                                                                                                                                                      |
|------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **ID** | RF-01                                                                                                                                                                                                                                            |
| **Nombre del requerimiento** | Autenticación de Usuarios                                                                                                                                                                                                                        |
| **Historia de usuario** | **Como** usuario del sistema (cliente, asesor, supervisor o gerente financiero), **quiero** ingresar mi usuario y contraseña, **para poder** acceder a las funcionalidades habilitadas según mi rol de manera segura.                            |
| **Descripción** | El sistema debe permitir que todos los tipos de usuario se autentiquen mediante usuario y contraseña, validar las credenciales ingresadas, mostrar un mensaje de error si son incorrectas, y redirigir al usuario según su rol si son correctas. |
| **Precondiciones** | El usuario debe estar previamente registrado en el sistema con un rol asignado (cliente, asesor, supervisor o gerente financiero).                                                                                                               |
| **Actor** | Cliente, Asesor, Supervisor, Gerente Financiero                                                                                                                                                                                                  |
| **Flujo principal** | 1. El actor ingresa su usuario y contraseña en el formulario de login. <br>2. El sistema valida las credenciales contra los registros almacenados. <br>3. El sistema redirige al actor al módulo correspondiente según su rol.                   |
| **Flujo alterno** | 2a. Si las credenciales son incorrectas, el sistema muestra un mensaje de error y solicita reingresar los datos.                                                                                                                                 |
| **Diagrama de caso de uso** | ![DiagramaR1](C:\Users\Kevyn\IdeaProjects\DOSW_Lab4_Inicial_Kevyn_Diego_Juliana\DOSW-Laboratorio4\docs\uml\DiagramaR1.png)                                                                                                                                                                                                             |
| **Poscondiciones** | Se espera como resultado que el usuario quede autenticado y con acceso únicamente a las funcionalidades permitidas por su rol.                                                                                                                   |

---

### 2.2 Requerimiento Funcional 4

| Campo | Descripción |
|------|-------------|
| **ID** | RF-04 |
| **Nombre del requerimiento** | Consulta de Saldo |
| **Historia de usuario** | **Como** cliente de Bankify, **quiero** seleccionar una de mis cuentas bancarias y consultar su saldo actual, **para poder** conocer el estado de mis finanzas en tiempo real sin necesidad de acudir a una sucursal. |
| **Descripción** | El sistema debe permitir al cliente autenticarse, seleccionar una de sus cuentas bancarias activas y visualizar el saldo disponible de la misma. |
| **Precondiciones** | El cliente debe estar autenticado en el sistema y tener al menos una cuenta bancaria activa registrada. |
| **Actor** | Cliente |
| **Flujo principal** | 1. El cliente se autentica en el sistema. <br>2. El cliente selecciona la cuenta bancaria que desea consultar. <br>3. El sistema valida que la cuenta esté activa y muestra el saldo disponible. |
| **Flujo alterno** | 3a. Si la cuenta está inactiva, el sistema muestra un mensaje indicando que la cuenta no está disponible para consulta. |
| **Diagrama de caso de uso** | ![DiagramaR4](C:\Users\Kevyn\IdeaProjects\DOSW_Lab4_Inicial_Kevyn_Diego_Juliana\DOSW-Laboratorio4\docs\uml\DiagramaR4.png)
| **Poscondiciones** | Se espera como resultado que el cliente visualice el saldo actualizado de la cuenta bancaria seleccionada. |

---

### 2.3 Requerimiento Funcional 5

| Campo | Descripción |
|------|-------------|
| **ID** | RF-05 |
| **Nombre del requerimiento** | Realizar Depósito |
| **Historia de usuario** | **Como** propietario de una cuenta, **quiero** ingresar el número de cuenta destino y el monto a depositar para confirmar la operación, **para poder** transferir dinero a una cuenta bancaria activa de forma controlada y segura. |
| **Descripción** | El sistema debe permitir al cliente propietario u otro usuario autenticado realizar un depósito a una cuenta bancaria activa, ingresando el número de cuenta destino y el monto, y actualizando el saldo una vez confirmada la operación. |
| **Precondiciones** | El usuario debe estar autenticado en el sistema. La cuenta destino debe existir, estar activa y pertenecer a un banco registrado. El monto del depósito debe ser mayor a 0. |
| **Actor** | Cliente (Propietario), Otro Usuario Autenticado |
| **Flujo principal** | 1. El actor se autentica en el sistema. <br>2. El actor ingresa el número de cuenta destino. <br>3. El sistema valida que la cuenta exista y esté activa. <br>4. El actor ingresa el monto del depósito. <br>5. El sistema valida que el monto sea mayor a 0. <br>6. El actor confirma la operación. <br>7. El sistema actualiza el saldo de la cuenta destino. |
| **Flujo alterno** | 3a. Si la cuenta no existe o está inactiva, el sistema muestra un mensaje de error. <br>5a. Si el monto es igual o menor a 0, el sistema muestra un mensaje de validación. |
| **Diagrama de caso de uso** | ![DiagramaR5](C:\Users\Kevyn\IdeaProjects\DOSW_Lab4_Inicial_Kevyn_Diego_Juliana\DOSW-Laboratorio4\docs\uml\DiagramaR5.png)
| **Poscondiciones** | Se espera como resultado que el saldo de la cuenta destino se haya incrementado con el monto depositado y que la operación quede registrada en el sistema. |

---

## 3. Preguntas

### 3.1 ¿Identifica algún requerimiento que deba detallarse más? ¿Cuál(es)?

Sí. El RF-05 (Realizar Depósito) requiere mayor detalle, especialmente en cuanto a quién puede depositar a qué cuentas, si existe un límite de monto por depósito, y si la operación debe quedar registrada con trazabilidad (fecha, hora, usuario que realizó el depósito).

### 3.2 ¿Existen requerimientos que se contradigan entre sí? ¿Cuál(es)?

No se identifican contradicciones directas. Sin embargo, el RF-05 genera ambigüedad: el caso de estudio indica que cualquier usuario autenticado puede depositar a cualquier cuenta, lo cual podría contradir principios de seguridad implícitos en el RF-01, donde el acceso debe estar controlado por roles.

### 3.3 ¿Cuáles deberían ser los 2 requerimientos más importantes en una primera iteración?

1. **RF-01 – Autenticación**, ya que es la base de seguridad sobre la que se apoyan todas las demás funcionalidades.
2. **RF-03 – Gestión de cuentas**, ya que sin cuentas registradas no es posible ejecutar ninguna operación financiera del sistema.

### 3.4 ¿Existe algún requerimiento que no debería realizarse?

El envío del reporte tributario a la DIAN en formato JSON (RF-07) no debería implementarse en esta primera versión del producto, ya que implica integración con un sistema externo real, lo cual añade complejidad técnica y legal innecesaria para validar el modelo de negocio en el MVP.

Mockup:
https://www.figma.com/make/CXNAN20UYPS36S63EukDuD/Bankify-Deposit-Flow-Mockup?t=DVKpY1o4PHQdVDJu-20&fullscreen=1&preview-route=%2Fdashboard