```mermaid
graph TD
    direction LR  % Esta línea debe ir aquí, justo después de graph TD

    subgraph Sistema de Gestión Hotelera (On-Premise)
        subgraph Módulo de Gestión de Reservas
            UC1[Registrar Reserva]
            UC2[Verificar Disponibilidad]
            UC3[Modificar Reserva]
            UC4[Cancelar Reserva]
        end

        subgraph Módulo de Gestión de Habitaciones
            UC5[Mostrar Estado Habitaciones]
            UC6[Actualizar Estado Habitación]
            UC7[Asignar Habitación Manualmente]
        end

        subgraph Módulo de Gestión de Empleados
            UC8[Gestionar Empleados]
            UC9[Asignar Rol a Empleado]
        end

        subgraph Módulo de Gestión de Reportes
            UC10[Generar Reporte Ocupación]
            UC11[Generar Reporte Ingresos]
            UC12[Exportar Reporte]
        end

        subgraph Módulo de Gestión de Clientes
            UC13[Gestionar Información de Cliente]
            UC14[Consultar Historial de Estadías]
        end

        subgraph Módulo de Gestión de Inventario
            UC15[Gestionar Productos/Suministros]
            UC16[Mostrar Stock Disponible]
            UC17[Actualizar Cantidad Inventario]
        end

        subgraph Módulo de Facturación
            UC18[Generar Factura]
        end

        subgraph Módulo de Configuración (Implícito)
            UC19[Configurar Parámetros Hotel]
        end

    end

    ActorAdmin[Administrador] --> UC19
    ActorAdmin --> UC8
    ActorAdmin --> UC9
    ActorAdmin --> UC10
    ActorAdmin --> UC11
    ActorAdmin --> UC12
    ActorAdmin --> UC15
    ActorAdmin --> UC16
    ActorAdmin --> UC17
    ActorAdmin --> UC13
    ActorAdmin --> UC14
    ActorAdmin --> UC1
    ActorAdmin --> UC2
    ActorAdmin --> UC3
    ActorAdmin --> UC4
    ActorAdmin --> UC5
    ActorAdmin --> UC6
    ActorAdmin --> UC7
    ActorAdmin --> UC18

    ActorRecepcionista[Recepcionista] --> UC1
    ActorRecepcionista --> UC2
    ActorRecepcionista --> UC3
    ActorRecepcionista --> UC4
    ActorRecepcionista --> UC5
    ActorRecepcionista --> UC6
    ActorRecepcionista --> UC7
    ActorRecepcionista --> UC13
    ActorRecepcionista --> UC14
    ActorRecepcionista --> UC18

    % RELACIONES CORREGIDAS
    UC1 -- extends --> UC2
    UC3 -- extends --> UC2
    UC18 -- uses --> UC13
    UC18 -- uses --> UC15
    UC18 -- uses --> UC17
