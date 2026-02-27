# DOSW Laboratorio 5 – Bankify

## **Semestre:** 2026-1

---

## **Integrantes del Equipo**

| **Integrante** | **Rol Scrum** | **GitHub** | **Contacto** |
|---|---|---|---|
| **Diego Alejandro Montes Bonilla** | Product Owner | [@banettchi](https://github.com/banettchi) | [diego.montes@mail.escuelaing.edu.co](mailto:diego.montes@mail.escuelaing.edu.co) |
| **Kevyn Daniel Forero Gonzalez** | Scrum Master | [@kevyn1005](https://github.com/kevyn1005) | [kevyn.forero@mail.escuelaing.edu.co](mailto:kevyn.forero@mail.escuelaing.edu.co) |
| **Maria Juliana Rodriguez Caicedo** | Desarrollador | [@JuliRodC](https://github.com/JuliRodC) | [maria.rodriguez@mail.escuelaing.edu.co](mailto:maria.rodriguez@mail.escuelaing.edu.co) |

---
## **Objetivo**

El objetivo de este laboratorio es apropiar diferentes usos de **Maven** para la gestión y construcción de proyectos Java. Se busca comprender la estructura y configuración de un proyecto Maven, el uso de arquetipos para la generación automatizada de la estructura del proyecto, la gestión de dependencias y la integración con herramientas de control de versiones como Git/GitHub mediante flujos de trabajo con ramas y pull requests.
---

---

## **Caso de Estudio: Bankify**

Bankify es una startup fintech que está desarrollando un sistema para la gestión básica de cuentas bancarias. En esta primera versión, se busca validar el modelo de negocio implementando únicamente funcionalidades esenciales: registro de cuentas, consulta de saldo, depósitos, y generación de reportes tributarios.

---

## **Estructura del Proyecto**

```
DOSW-Laboratorio5/
├── pom.xml
├── README.md
├── docs/
│   └── planning/
│       └── scrum_work_breakdown.md   ← Épicas, HU, tareas y estimaciones
└── src/
    ├── main/java/edu/dosw/lab/
    │   └── App.java
    └── test/java/edu/dosw/lab/
        └── AppTest.java
```

---

## **Estimación con Planning Poker**


### ¿Cuál fue la mayor dificultad a la hora de estimar?

La mayor dificultad fue ponernos de acuerdo en el nivel de complejidad técnica de cada historia de usuario. Cada integrante del equipo tenia una idea diferente, lo que generó diferencias notables en algunas votaciones. En particular, la HU-04 fue la más difícil de estimar porque involucra múltiples capas del sistema, lo que generó interpretaciones muy distintas sobre su esfuerzo real.


### ¿Fue fácil llegar a un consenso?

En general, no fue completamente fácil. Para las historias más simples como HU-01 y HU-03 el consenso fué rapido, ya que todos estabamos de acuerdo en que las tareas eran menos complejas. Sin embargo, para HU-02 y especialmente HU-04 fue necesario ponernos a hablar mas tiempo para poder llegar a un acuerdo. El hecho de que Planning Poker obliga a revelar todas las cartas al mismo tiempo fue útil porque evitó que las primeras opiniones influenciaran a los demás antes de que todos pensaramos de forma independiente.

---

### ¿Cómo resolvieron los escenarios donde las estimaciones para la misma historia de usuario no fueron cercanas?

Para cumplir con el Planning Poker que pedía el laboratorio, nos reunimos los tres y nos pusimos a votar cada historia de usuario. La dinámica fue así: cada uno decía un número y después explicábamos por qué creíamos que esa tarea se iba a demorar más o menos.

Al principio no todos pensábamos igual; por ejemplo, uno veía algo fácil y otro veía que la base de datos estaba complicada. Así que, mientras hablábamos y cada uno daba su punto de vista técnico, fuimos cambiando los números que habíamos pensado al principio. Seguimos discutiendo y votando hasta que al final todos estuvimos de acuerdo en un mismo valor para cada historia y ese fue el que dejamos como definitivo.

---

