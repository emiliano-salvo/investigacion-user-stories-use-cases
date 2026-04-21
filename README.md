# Ficha Técnica: User Stories / Use Cases
### Curso: Fundamentos de Ingeniería de Software Integrantes: Felipe Lecot, Nahuel Merlo, Emiliano Salvo

## 1. Fuentes de Información
- Material complemenatrio: Historias de usuario (aulas) : https://www.scrummanager.com/files/scrum_manager_historias_usuario.pdf
- Visual paradigm: https://www.visual-paradigm.com/guide/uml-unified-modeling-language/what-is-uml/

## 2. Definiciones
### Historias de usuario
Las historias de usuario son una herramienta que agiliza la administración de requisitos, reduciendo la cantidad de documentos formales y tiempo necesarios. Se usan, en el contexto de la ingeniería de requisitos ágil, como una herramienta de comunicación que combina las fortalezas de ambos medios: escrito y verbal. Describen, en una o dos frases, una funcionalidad de software desde el punto de vista del usuario, con el lenguaje que éste emplearía (Mike Cohn 2004). El foco está
puesto en qué necesidades o problemas soluciona lo que se va a construir.
## Anatomía de las historias

Es preferible no adoptar formatos rígidos. Además de los campos necesarios, también podemos incluir aquellos que proporcionen información útil.

> **El objetivo es construir un entendimiento compartido**

---

## Campos relevantes

| Campo | Detalles |
| :--- | :--- |
| **Título** | - |
| **ID** | - |
| **Descripción** | Debe responder a:<br>• ¿Quién se beneficia?<br>• ¿Qué se quiere?<br>• ¿Cuál es el beneficio? |
| **Estimación** | Aproximación relativa del trabajo requerido. Considerar la incertidumbre.<br>Se recomienda:<br>• Secuencia de Fibonacci (1, 2, 3, 5, 8, 13...)<br>• Talles (XS, S, M, L, XL) |
| **Valor de negocio** | Se considera cuánto está dispuesto a pagar el cliente. Es un campo volátil (se recomienda usar escala de Fibonacci). |
| **Prioridad** | Clasificación:<br>• Must have<br>• Should have<br>• Could have<br>• Won't have |
| **Criterios de aceptación** | Método **SMART** (Specific, Measurable, Achievable, Relevant, Time-Boxed).<br><br>**Estrategia:**<br>Escenario [número] [título]<br>Dado que [contexto]<br>Cuando [evento]<br>Entonces [resultados] |

### Casos de Uso
Los casos de uso son otra técnica más que a veces se incorpora en los procesos ágiles,
pero no son equivalentes a las historias de usuario. Conviene diferenciar los unos de las
otras para evitar confusiones.

Un caso de uso captura la funcionalidad deseada desde la perspectiva de los usuarios
(actores) y cómo interactúan con el sistema. Se escriben usando UML (unified modeling
language) en los diagramas de casos de uso. UML es un lenguaje de modelado para
describir, de forma sencilla, un sistema desde sus perspectivas estática y dinámica.

Sus componentes son:
- Actores: los roles que interactúan con el sistema.
- Precondiciones: estado del sistema antes de ejecutar el caso de uso.
- Flujo principal: secuencia de pasos en el escenario exitoso.
- Flujos alternativos: variaciones del flujo principal.
- Flujos de excepción: qué ocurre cuando algo falla.
- Postcondiciones: estado del sistema después de ejecutar el caso de uso.

### UML
UML , acrónimo de Lenguaje Unificado de Modelado, es un lenguaje de modelado estandarizado que consta de un conjunto integrado de diagramas, desarrollado para ayudar a los desarrolladores de sistemas y software a especificar, visualizar, construir y documentar los artefactos de los sistemas de software, así como para el modelado de negocios y otros sistemas no relacionados con el software.

## 3. Demostracion practica
---

### 3.1. Historia de Usuario: "Préstamo de Libro"

**Como** Bibliotecario, **quiero** registrar el préstamo de un libro a un socio, **para** mantener un control de quién tiene cada ejemplar y cuándo debe devolverlo.

**Criterios de Aceptación:**

- El sistema debe verificar que el libro esté disponible.
- Se debe registrar la fecha de inicio y la fecha de devolución (7 días después).
- Un socio no puede llevarse un libro si tiene deudas pendientes.

---

### 3.2. Casos de Uso

1. **Registrar Préstamo:** El bibliotecario ingresa el ID del socio y el ID del libro para crear el registro.
2. **Consultar Disponibilidad:** El sistema verifica si el libro está en estante o ya está prestado.
3. **Registrar Devolución:** El bibliotecario marca el libro como disponible nuevamente al recibirlo.

---

### 3.3. Modelo de Dominio

- **Socio:** Atributos como `nombre`, `idSocio`, `estadoCuenta`.
- **Libro:** Atributos como `titulo`, `idLibro`, `disponible` (booleano).
- **Préstamo:** Esta es la clase "vínculo". Atributos como `fechaInicio`, `fechaDevolucion`.

- Un **Socio** tiene muchos **Préstamos**.
- Un **Libro** puede estar en muchos **Préstamos** (a lo largo del tiempo), pero solo en uno activo a la vez.
- El **Préstamo** conecta al **Socio** con el **Libro**.
