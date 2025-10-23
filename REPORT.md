# Lab 3 Complete a Web API -- Project Report

## Description of Changes 
- Se completaron los tests en `ControllerTests.kt` para verificar seguridad de los endpoints REST del `EmployeeController`.
    - POST /employees: añadido setup para que `save` devuelva IDs distintos en llamadas consecutivas; verificación de que `save` se llamó exactamente dos veces y que no se invocaron métodos de lectura/eliminación.
    - GET /employees/{id}: añadido setup para que `findById(1)` devuelva un empleado y `findById(2)` devuelva vacío; se realizaron dos lecturas para comprobar idempotencia y verificación de que no hubo modificaciones (`save`/`deleteById` no llamadas).
    - PUT /employees/{id}: añadido setup con `findById` que devuelve vacío en la primera llamada y el empleado en la segunda (simula create luego update); `save` configurado para devolver el empleado actualizado; verificación de llamadas a `findById` y `save` dos veces.
    - DELETE /employees/{id}: añadido `justRun` para permitir `deleteById` sin efecto; dos borrados invocados y verificación de que `deleteById` fue llamado exactamente dos veces, sin otras llamadas al repositorio.
## Technical Decisions
Se han seguido las prácticas propuestas en el guión y la estructura de código facilitada. Además he ejecutado ./gradlew ktlintFormat para dar formato correcto al código añadido.
## Learning Outcomes
He aprendido a usar el verify en los test y dar una estructura de los mensajes y respuestas esperadas con setup.
## AI Disclosure
### AI Tools Used
- ChatGPT
### AI-Assisted Work
Ayuda a redacción del Report.md pasándole como entrada redacción enteera mía previa para corregir sintaxis y formalidad. Estoy aprovechando a empezar a redactar con IA para mejorar las memorias.
### Original Work
El REPORT.md lo he redactado yo mismo, después lo he mandado a ChatGPT para que me ayudara a mejorar la redacción y formalidad del texto.
El código lo he escrito yo siguiendo las indicaciones del guión y la estructura facilitada.