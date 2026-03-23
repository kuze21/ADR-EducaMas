ADR 001: Implementación de Almacenamiento y Entrega de Video mediante AWS Serverless
Estado: Aceptado
Fecha: 2026-03-22
Autor:Álvaro Cabezas
      Roberth Groom

1. Contexto y Problema
La plataforma "EducaMás" requiere una infraestructura capaz de gestionar altas cantidades de material para clases virtuales con alta cantidad de usuarios simultáneos.

Desafío: Garantizar baja latencia global y alta disponibilidad con un presupuesto limitado y sin personal dedicado exclusivamente al mantenimiento de servidores físicos.

Requisitos Clave: Seguridad de contenido (evitar descargas no autorizadas) y escalabilidad automática ante la demanda variable de los estudiantes.

2. Decisión
Se decide adoptar una Arquitectura de Entrega de Contenido (CDN) basada en AWS, utilizando los siguientes servicios gestionados:

Amazon S3: Como origen de almacenamiento de objetos (videos).

Amazon CloudFront: Como red de distribución de contenido (CDN) para cachear videos en ubicaciones cercanas al usuario (Edge Locations).

Origin Access Control (OAC): Para restringir el acceso al bucket S3, permitiendo que los videos solo sean accesibles a través de CloudFront.

Alternativas Consideradas
Opción B (Servidores Propios): Descartada por el alto costo inicial por mantención, desarrollo y la complejidad de configurar balanceadores de carga y replicación de datos manualmente para multiples usuarios.

3. Justificación Técnica 
Eficiencia de Rendimiento: CloudFront reduce el tiempo de carga (TTFB) al distribuir el tráfico. S3 escala de forma casi infinita sin intervención manual.

Optimización de Costos: Se elimina el gasto en hardware ocioso; AWS solo cobra por el almacenamiento real y los datos transferidos.

Seguridad: El uso de OAC asegura que nadie pueda saltarse la CDN para descargar videos directamente del servidor de origen.

4. Consecuencias
Positivas: Reducción drástica del tiempo de mantenimiento. El equipo puede enfocarse en el desarrollo de la app y no en los discos duros.

Negativas: Dependencia del proveedor (AWS). Los costos mensuales fluctuarán según el tráfico de los estudiantes.

Riesgos: Si no se configuran alertas de presupuesto (AWS Budgets), un pico inesperado de tráfico podría elevar la factura.
