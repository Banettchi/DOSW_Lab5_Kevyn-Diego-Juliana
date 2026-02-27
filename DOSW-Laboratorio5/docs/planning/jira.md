# 📄 Planeación del Sistema en Jira

## Desglose de trabajo: Épicas, Historias de Usuario y Tareas

La implementación de los requerimientos identificados de Bankify se desglosa de la siguiente manera:

---

### 1. Épica

#### EP-01 – Gestión de Depósitos Bancarios
![Jira1.png](../images/Jira1.png)

![Jira2.png](../images/Jira2.png)
---

### 2. Historias de Usuario

#### HU-01 – Ingresar número de cuenta destino
![Jira3.png](../images/Jira3.png)

#### HU-02 – Validar existencia y estado de la cuenta destino
![Jira4.png](../images/Jira4.png)

#### HU-03 – Ingresar y validar monto del depósito
![Jira5.png](../images/Jira5.png)
#### HU-04 – Confirmar depósito y actualizar saldo
![Jira6.png](../images/Jira6.png)


---

### 3. Tareas

#### TR-01 – Diseñar formulario de ingreso de cuenta destino
![Jira7.png](../images/Jira7.png)
#### TR-02 – Crear endpoint REST para recibir el número de cuenta destino
![Jira8.png](../images/Jira8.png)

#### TR-03 – Mostrar mensaje de error si el campo está vacío
![Jira9.png](../images/Jira9.png)
#### TR-04 – Implementar lógica de consulta y validación de cuenta en el servicio
![Jira10.png](../images/Jira10.png)
#### TR-05 – Implementar endpoint REST de validación de cuenta en el controlador
![Jira11.png](../images/Jira11.png)
#### TR-06 – Mostrar mensaje de error si la cuenta no es válida
![Jira12.png](../images/Jira12.png)
#### TR-07 – Diseñar campo de ingreso del monto
![Jira13.png](../images/Jira13.png)
#### TR-08 – Validar que el monto sea mayor a cero en el frontend
![Jira14.png](../images/Jira14.png)
#### TR-09 – Validar monto en el backend
![Jira15.png](../images/Jira15.png)
#### TR-10 – Implementar lógica de actualización de saldo
![Jira16.png](../images/Jira16.png)
#### TR-11 – Registrar transacción en el historial
![Jira17.png](../images/Jira17.png)
#### TR-12 – Mostrar confirmación del depósito al usuario
![Jira18.png](../images/Jira18.png)
---

### 4. Cronograma
![Jira19.png](../images/Jira19.png)
---

### 5. Sprint Backlog
![Jira20.png](../images/Jira20.png)

> **Justificación de la planeación:**
El proyecto está configurado en Jira bajo el framework Kanban.
Para representar el primer sprint se incluyeron las historias
HU-01, HU-02 y HU-03 (11 puntos en total) en estado "En Proceso",
dado que tienen prioridad Alta. La HU-04 queda pendiente para el
siguiente sprint por tener prioridad Media y mayor complejidad
(8 puntos). Las tareas fueron asignadas a cada integrante del equipo
según su rol 