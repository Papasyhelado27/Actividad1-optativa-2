   Resumen
   
   Esta labor convierte las exigencias detectadas en el análisis arquitectónico en especificaciones funcionales, características de calidad y parámetros de evaluación.
   
   El propósito es evaluar distintas alternativas estructurales y elegir una propuesta preliminar que satisfaga las demandas del negocio, teniendo en cuenta costos, complejidad, riesgos y capacidades de adaptación.
   
   Requisitos prioritarios
   
   Los requisitos prioritarios incluyen el registro de pedidos, la prevención de duplicados, la validación de inventario, la gestión de estados, la asignación de entregas, la trazabilidad, las integraciones externas y el control de acceso.
   
   Además, se definen metas iniciales de rendimiento, disponibilidad, seguridad, integridad y facilidad de adaptación.
   
   Decisión arquitectónica inicial
   
   Se sugiere un monolito modular que establezca límites claros entre pedidos, inventario, entregas, trazabilidad, incidencias e integraciones externas.
   
   Esta alternativa facilita el control de la complejidad inicial, organiza el sistema de acuerdo con las responsabilidades y mantiene la opción de avanzar hacia servicios independientes si las demandas del negocio lo requieren.
   
   
   
   
   Plataforma logística — Actividad 3
   
   1. Descripción del proyecto
   
   Este proyecto sugiere una plataforma logística diseñada para facilitar la gestión de entregas en la última milla. La solución tiene como objetivo organizar el proceso de asignación de repartidores y establecer directrices claras para evitar errores durante la operación.
   
   La propuesta se desarrolla de manera gradual, documentando el problema, el modelo de dominio, los casos de uso y las decisiones arquitectónicas.
   
   
   
   2. Objetivo
   
   Establecer una arquitectura que facilite la gestión de entregas y la asignación de repartidores de manera organizada, manteniendo separadas las reglas del negocio de los detalles técnicos relacionados con el almacenamiento e infraestructura.
   
   3. Alcance de la propuesta
   
   El flujo principal seleccionado es la asignación de un repartidor a una entrega. Este proceso incluye:
   
   Identificar la entrega que se asignará.
   
   Verificar que la entrega esté registrada.
   
   Evitar que una entrega tenga más de un repartidor asignado.
   
   Registrar la asignación cuando se cumplen las reglas establecidas.
   
   La verificación de la disponibilidad del repartidor, las notificaciones y otras integraciones son aspectos que podrían ampliarse en el futuro.
   
   4. Modelo de dominio
   
   El modelo incluye los siguientes componentes:
   
   Delivery: entidad que representa una entrega y salvaguarda sus reglas de negocio.
   
   DeliveryId: objeto de valor que identifica una entrega.
   
   DeliveryAddress: objeto de valor que representa la dirección de entrega.
   
   CourierId: identificador del repartidor asignado.
   
   La regla principal establecida es que una entrega no puede recibir una segunda asignación si ya tiene un repartidor asignado.
   
   5. Arquitectura propuesta
   
   La solución se estructura en tres capas:
   
   Dominio: contiene la entidad Delivery, los objetos de valor y las reglas de negocio.
   
   Aplicación: incluye AssignCourierUseCase, que coordina el proceso de asignación.
   
   Infraestructura: implementa el acceso al repositorio y al almacenamiento.
   
   El caso de uso opera con el contrato IDeliveryRepository, en lugar de depender directamente de una tecnología específica de base de datos. Esto facilita las pruebas, el mantenimiento y los posibles cambios tecnológicos.
   
   6. Diagramas de arquitectura
   
   Diagrama C4

   
   
   

   Este diagrama ofrece una visión general de la plataforma logística, sus actores y los principales componentes y relaciones.
   
   Diagrama de capas
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   
   Este diagrama ilustra la separación entre dominio, aplicación e infraestructura, destacando las responsabilidades principales de cada capa.
