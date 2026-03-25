# **REQUISITOS FUNCIONALES**

## RF-001: GESTIÓN DE COTIZACIONES EN LÍNEA
**RF-001.1: Creación de Cotización por el Cliente**
* **Descripción:** El sistema debe permitir que el cliente realice su cotización directamente desde la página web sin necesidad de contacto físico con el jefe.
* **Actor:** Cliente externo
* **Precondiciones:** Cliente tiene acceso a la página web
* **Flujo Principal:**
    1) Cliente accede a la página web de Casetech
    2) Sistema presenta formulario de cotización
    3) Cliente ingresa tipo de material, cantidad y datos de contacto
    4) Sistema calcula precio automáticamente
    5) Sistema genera cotización y la envía al cliente por correo
* **Criterios de Aceptación:**
    * Cotización generada sin intervención del jefe.
    * Confirmación enviada al cliente en menos de 5 minutos.
    * Cotización guardada en el sistema.
* **Prioridad:** MUST (Crítico)

---

## RF-002: SEGUIMIENTO DE PEDIDOS
**RF-002.1: Consulta de Estado del Pedido**
* **Descripción:** El sistema debe permitir al cliente consultar en qué etapa se encuentra su material.
* **Actor:** Cliente externo
* **Precondiciones:** Cliente tiene un pedido activo.
* **Flujo Principal:**
    1. Cliente ingresa su número de pedido en la página web.
    2. Sistema muestra el estado actual: en producción, alistamiento o entrega.
    3. Sistema muestra fecha estimada de entrega.
* **Criterios de Aceptación:**
    * Estados visibles en tiempo real.
    * Notificación automática al cliente cuando cambia el estado.
* **Prioridad:** MUST (Crítico)

---

## RF-003: GESTIÓN DE BODEGA
**RF-003.1: Registro de Entrada y Salida de Material**
* **Descripción:** El sistema debe registrar automáticamente los movimientos de inventario en bodega.
* **Actor:** Operario de bodega
* **Precondiciones:** Usuario operario autenticado en el sistema.
* **Flujo Principal:**
    1. Operario registra entrada o salida de material.
    2. Sistema actualiza inventario automáticamente.
    3. Sistema genera alerta si el stock baja del mínimo establecido.
* **Criterios de Aceptación:**
    * Inventario actualizado en tiempo real.
    * Historial de movimientos consultable.
    * Alertas automáticas de bajo inventario.
* **Prioridad:** MUST (Crítico)

---

## RF-004: ALERTAS Y SUGERENCIA DE PROVEEDORES
**RF-004.1: Notificación de Material Agotado**
* **Descripción:** El sistema debe notificar al cliente cuando un material no esté disponible y sugerir proveedores alternativos.
* **Actor:** Sistema automático
* **Precondiciones:** Inventario actualizado en el sistema.
* **Flujo Principal:**
    1. Sistema detecta material con stock bajo o agotado.
    2. Sistema envía alerta automática al cliente.
    3. Sistema muestra lista de proveedores sugeridos con precio y calidad.
    4. Cliente selecciona proveedor de su preferencia.
* **Criterios de Aceptación:**
    * Alerta enviada en tiempo real.
    * Mínimo 3 opciones de proveedores sugeridos.
    * Proveedores ordenados por precio y calidad.
* **Prioridad:** SHOULD (Importante)

---

## RF-005: AUTENTICACIÓN Y ROLES DE USUARIO
**RF-005.1: Registro e Inicio de Sesión**
* **Descripción:** El sistema debe permitir a los usuarios autenticarse y acceder según su rol asignado.
* **Actor:** Administrador, operario, cliente
* **Precondiciones:** Usuario registrado en el sistema.
* **Flujo Principal:**
    1. Usuario ingresa correo y contraseña.
    2. Sistema valida credenciales.
    3. Sistema redirige al módulo correspondiente según rol: admin, operario o cliente.
* **Criterios de Aceptación:**
    * Roles diferenciados con permisos distintos.
    * Bloqueo automático tras 5 intentos fallidos.
    * Sesión cerrada automáticamente tras 30 minutos de inactividad.
* **Prioridad:** MUST (Crítico)

---

## RF-006: GESTIÓN DE PEDIDOS
**RF-006.1: Registro y Actualización de Pedidos**
* **Descripción:** El sistema debe registrar cada pedido y permitir actualizarlo a través de sus etapas.
* **Actor:** Operario / Administrador
* **Precondiciones:** Cotización aprobada por el cliente.
* **Flujo Principal:**
    1. Operario crea pedido a partir de cotización aprobada.
    2. Sistema asigna número único al pedido.
    3. Operario actualiza estado: producción, alistamiento, entrega.
    4. Sistema notifica al cliente en cada cambio de estado.
* **Criterios de Aceptación:**
    * Número de pedido único y rastreable.
    * Notificaciones automáticas al cliente.
    * Historial completo de estados del pedido.
* **Prioridad:** MUST (Crítico)

---

## RF-007: REPORTES Y ESTADÍSTICAS
**RF-007.1: Generación de Reportes para el Administrador**
* **Descripción:** El sistema debe generar reportes de ventas, inventario y pedidos para el administrador.
* **Actor:** Administrador
* **Precondiciones:** Datos registrados en el sistema.
* **Flujo Principal:**
    1. Administrador selecciona tipo de reporte y rango de fechas.
    2. Sistema genera reporte con los datos solicitados.
    3. Sistema permite exportar en PDF o Excel.
* **Criterios de Aceptación:**
    * Reportes exportables en PDF y Excel.
    * Generación del reporte en menos de 3 segundos.
    * Datos actualizados en tiempo real.
* **Prioridad:** SHOULD (Importante)

---

## RF-008: GESTIÓN DE PROVEEDORES
**RF-008.1: Registro y Consulta de Proveedores**
* **Descripción:** El sistema debe permitir registrar, editar y consultar proveedores con información de precio y calidad.
* **Actor:** Administrador
* **Precondiciones:** Administrador autenticado en el sistema.
* **Flujo Principal:**
    1. Administrador accede al módulo de proveedores.
    2. Sistema presenta formulario para agregar o editar proveedor.
    3. Administrador ingresa nombre, contacto, materiales que ofrece y precio.
    4. Sistema guarda la información para sugerencias automáticas.
* **Criterios de Aceptación:**
    * Proveedores consultables desde el módulo de bodega.
    * Información actualizable en cualquier momento.
    * Proveedor asociado a los materiales que suministra.
* **Prioridad:** SHOULD (Importante)

---

## RF-009: PANEL DE ADMINISTRACIÓN
**RF-009.1: Vista General para el Administrador**
* **Descripción:** El sistema debe mostrar al administrador un resumen del estado actual de pedidos, inventario y cotizaciones.
* **Actor:** Administrador
* **Precondiciones:** Administrador autenticado en el sistema.
* **Flujo Principal:**
    1. Administrador accede al panel principal.
    2. Sistema muestra resumen de pedidos activos, inventario y cotizaciones pendientes.
    3. Administrador puede acceder a cada módulo desde el panel.
* **Criterios de Aceptación:**
    * Información actualizada en tiempo real.
    * Acceso a todos los módulos en máximo 2 clics.
    * Resumen visual claro y fácil de interpretar.
* **Prioridad:** MUST (Crítico)

---

## RF-010: NOTIFICACIONES AL CLIENTE
**RF-010.1: Envío de Notificaciones por Correo Electrónico**
* **Descripción:** El sistema debe enviar notificaciones automáticas al cliente sobre cambios en el estado de su pedido.
* **Actor:** Sistema automático
* **Precondiciones:** Cliente con pedido activo y correo registrado.
* **Flujo Principal:**
    1. Sistema detecta cambio de estado en un pedido.
    2. Sistema genera correo automático con el nuevo estado.
    3. Sistema envía notificación al correo del cliente.
    4. Sistema registra el envío en el historial del pedido.
* **Criterios de Aceptación:**
    * Notificación enviada en menos de 2 minutos tras el cambio.
    * Correo con información clara del estado y número de pedido.
    * Registro de todas las notificaciones enviadas.
* **Prioridad:** SHOULD (Importante)

---

## RF-011: HISTORIAL DE COTIZACIONES
**RF-011.1: Consulta de Cotizaciones Anteriores**
* **Descripción:** El sistema debe permitir al cliente consultar el historial de sus cotizaciones previas.
* **Actor:** Cliente externo
* **Precondiciones:** Cliente autenticado con cotizaciones registradas.
* **Flujo Principal:**
    1. Cliente accede a su perfil en la página web.
    2. Sistema muestra listado de cotizaciones anteriores.
    3. Cliente selecciona una cotización para ver detalle.
    4. Sistema muestra materiales, cantidades, precio y fecha.
* **Criterios de Aceptación:**
    * Historial disponible desde el perfil del cliente.
    * Cotizaciones ordenadas por fecha más reciente.
    * Opción de repetir una cotización anterior.
* **Prioridad:** COULD (Deseable)

---

## RF-012: RECUPERACIÓN DE CONTRASEÑA
**RF-012.1: Restablecimiento de Contraseña**
* **Descripción:** El sistema debe permitir a los usuarios recuperar el acceso a su cuenta en caso de olvidar su contraseña.
* **Actor:** Cualquier usuario registrado
* **Precondiciones:** Usuario con correo electrónico registrado en el sistema.
* **Flujo Principal:**
    1. Usuario selecciona la opción de "olvidé mi contraseña".
    2. Sistema solicita correo electrónico registrado.
    3. Sistema envía enlace de restablecimiento al correo.
    4. Usuario ingresa nueva contraseña.
    5. Sistema actualiza contraseña y redirige al inicio de sesión.
* **Criterios de Aceptación:**
    * Enlace de restablecimiento válido por máximo 30 minutos.
    * Confirmación de cambio exitoso por correo.
    * Nueva contraseña debe cumplir mínimo 8 caracteres.
* **Prioridad:** MUST (Crítico)