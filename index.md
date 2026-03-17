¿Qué es un ADR?
  Un Architecture Decision Record (ADR) es un documento que describe una decisión importante de arquitectura en un proyecto.
Incluye:
  • contexto del problema
  • decisión tomada
  • consecuencias de la decisión
Su objetivo es registrar por qué se tomó una decisión técnica.

Alcance del proceso ADR
Se debe crear un ADR para decisiones arquitectónicas importantes como:
  • patrones de arquitectura (ej. microservicios)
  • requisitos no funcionales (seguridad, disponibilidad)
  • dependencias entre componentes
  • interfaces o APIs
  • herramientas, frameworks o procesos utilizados
Estas decisiones influyen directamente en el diseño del sistema.

Contenido de un ADR
Un ADR debe incluir al menos:
1. Contexto
  Describe el problema y las alternativas.
2. Decisión
  Explica la solución adoptada.
3. Consecuencias
  Describe ventajas, desventajas e impactos.
El foco del ADR es explicar el motivo de la decisión, no solo la implementación.

Proceso de creación y adopción
El proceso de un ADR sigue estas etapas:
  1. Identificación de la decisión arquitectónica
  2. Creación del ADR en estado Proposed
  3. Revisión por el equipo
  4. Discusión y comentarios
  5. Decisión final
Resultados posibles:
  • Accepted → decisión aprobada
  • Rejected → decisión rechazada
  • Rework → necesita modificaciones.

Uso del ADR en el proyecto
Los ADR forman un registro de decisiones (decision log).
Este registro se utiliza para:
  • revisar decisiones durante code reviews
  • validar cambios en la arquitectura
  • entender el contexto del proyecto
El historial de ADR permite conocer todas las decisiones tomadas durante el desarrollo.

Actualización de decisiones
Una vez aceptado o rechazado, un ADR se considera inmutable.
Si se necesita cambiar la decisión:
  1. Se crea un nuevo ADR
  2. El ADR anterior se marca como Superseded (reemplazado).
Esto mantiene un historial claro de decisiones arquitectónicas.

Conclusión
El proceso ADR permite:
  • documentar decisiones arquitectónicas
  • mejorar la comunicación del equipo
  • mantener un historial técnico del proyecto
  • evitar repetir discusiones técnicas
Los ADR ayudan a alinear equipos y mejorar la gestión de la arquitectura de software.





ADR-001 
Decisión sobre el almacenamiento de videos (cambiar)

Contexto
-	Problema
-	Factores relevantes
-	Alternativas a considerar:
Opción A: Almacenamiento en la nube con CDN (Red de Entrega de Contenido): Utilizar un servicio de almacenamiento en la nube como AWS S3 o Google Cloud Storage, combinado con una CDN para la entrega eficiente de los videos a los usuarios.

Opción B: Almacenamiento en servidores propios: Mantener los videos en servidores propios de la empresa
Decisión
-	Explicación
-	Pros y contras
Consecuencias
-	Impacto
-	Ventajas
-	Desventajas
-	Impactos

