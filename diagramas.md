```mermaid
graph TD
    ActorRecepcionista[Recepcionista] --> UC1[Registrar Nueva Reserva]
    ActorRecepcionista --> UC2[Modificar Reserva Existente]
    ActorRecepcionista --> UC3[Cancelar Reserva Existente]
    ActorRecepcionista --> UC4[Realizar Check-in]
    ActorRecepcionista --> UC5[Realizar Check-out]
    ActorRecepcionista --> UC6[Asignar Habitación Manualmente]
    ActorRecepcionista --> UC7[Consultar Estado de Habitaciones]
    ActorRecepcionista --> UC8[Registrar Huésped Nuevo]
    ActorRecepcionista --> UC9[Consultar Historial de Huésped]
    ActorRecepcionista --> UC10[Generar Factura de Estadía]

    UC1 -- includes --> UC11[Verificar Disponibilidad]
    UC2 -- includes --> UC11

    UC4 -- includes --> UC12[Actualizar Estado Habitación a Ocupada]
    UC5 -- includes --> UC13[Actualizar Estado Habitación a Limpieza]

    UC10 -- uses --> UC9
    UC10 -- includes --> UC14[Registrar Pagos]
