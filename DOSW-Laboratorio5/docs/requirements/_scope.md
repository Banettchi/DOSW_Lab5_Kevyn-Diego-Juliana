# 📄 Requerimientos del Sistema

## 1. Sistema
* **Nombre del sistema:** Bankify
* **Objetivo:** El sistema tiene como objetivo proporcionar una plataforma web para la gestión básica de cuentas bancarias, permitiendo a los clientes consultar saldos, realizar depósitos y generar reportes tributarios, garantizando que las cuentas cumplan las reglas de negocio definidas y que los usuarios interactúen con ellas de forma sencilla y segura.

## 2. Problema a resolver

Actualmente, Bankify no cuenta con un sistema centralizado que permita registrar cuentas bancarias de manera validada, consultar saldos, realizar depósitos de forma controlada, generar reportes tributarios para clientes en formato PDF y enviar reportes a la DIAN en formato JSON. Esto impide que la startup pueda operar de manera organizada y segura, dificultando tanto la gestión interna de clientes y cuentas como el cumplimiento de obligaciones tributarias ante entidades externas como la DIAN.

## 3. Diagrama de Contexto

### 3.1 Diagrama

![Diagrama Contexto](Images/Dia_Contexto.png)

### 3.2 Actores

| Actor / Rol           | Descripción                                                                 |
|-----------------------|:---------------------------------------------------------------------------:|
| Cliente               | Usuario final que consulta saldos, realiza depósitos y genera reportes PDF de su declaración de renta |
| Asesor                | Empleado de Bankify autorizado para crear, activar, inactivar y actualizar cuentas bancarias |
| Supervisor            | Empleado autorizado para crear, activar, inactivar, actualizar y eliminar clientes del sistema |
| Gerente Financiero    | Responsable de generar y enviar los reportes tributarios de todas las cuentas a la DIAN |

### 3.3 Sistemas externos

| Sistema              | Descripción                                                                                      |
|----------------------|:------------------------------------------------------------------------------------------------:|
| DIAN                 | Entidad tributaria colombiana que recibe los reportes de declaración de renta en formato JSON    |
| Bancos Registrados   | Entidades bancarias registradas en el sistema (ej. Bancolombia, Davivienda) utilizadas para validar los dos primeros dígitos del número de cuenta |

## 4. Alcance del sistema

### 4.1 Dentro del sistema
1. Autenticación de usuarios (clientes, asesores, supervisores y gerente financiero) mediante usuario y contraseña.
2. Gestión de clientes: creación, activación, inactivación, actualización y eliminación de clientes por parte del supervisor.
3. Gestión de cuentas bancarias: creación, activación, inactivación y actualización por parte del asesor; inactivación por parte del cliente.
4. Consulta de saldo de cuentas por parte del cliente.
5. Realización de depósitos a cuentas bancarias por parte del cliente propietario u otros usuarios.
6. Generación de reporte tributario de declaración de renta en formato PDF para el cliente.
7. Generación y envío de reportes tributarios de todas las cuentas a la DIAN en formato JSON por parte del gerente financiero.
8. Validación de números de cuenta: exactamente 10 dígitos numéricos y pertenecientes a un banco registrado.

### 4.2 Fuera del sistema
1. Procesamiento de pagos a terceros o transferencias entre bancos externos.
2. Gestión de productos financieros complejos como créditos, inversiones o seguros.
3. Integración directa con los sistemas internos de los bancos registrados para sincronización de saldos en tiempo real.
4. Soporte para múltiples monedas o transacciones en divisas extranjeras.