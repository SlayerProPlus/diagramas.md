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

    UC1 .> UC11(Verificar Disponibilidad) : <<includes>>
    UC2 .> UC11 : <<includes>>
    UC4 .> UC12(Actualizar Estado Habitación a Ocupada) : <<includes>>
    UC5 .> UC13(Actualizar Estado Habitación a Limpieza) : <<includes>>
    UC10 .> UC9 : <<uses>>
    UC10 .> UC14(Registrar Pagos) : <<includes>>
