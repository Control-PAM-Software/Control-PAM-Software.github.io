# Configuración

Accedé desde la barra de menú superior: **Menú → Configuración**.

La ventana de configuración tiene un **submenú lateral izquierdo** con dos tipos de entradas:

- **Sistema** — configuraciones generales que aplican a todos los módulos.
- **Líneas** (AB, Atos, Bernafon, Inomed, Oticom) — configuraciones específicas por proveedor.

<!-- PLACEHOLDER: Captura de la ventana de Configuración del Sistema -->

![Configuración del Sistema](_media/Configuracion/Configuracion.png)

---

## Sistema (General)

En el submenú **Sistema** podés configurar:

### Colores de visualización

![Configuracion Colores](_media/Configuracion/Configuracion_Colores.png)

| Campo                    | Uso                                                                              |
| ------------------------ | -------------------------------------------------------------------------------- |
| **Color de diferencias** | Resalta filas con cantidad, número de serie o vencimiento distinto a lo esperado |
| **Color de faltantes**   | Resalta artículos presentes en el Anexo pero no encontrados en la Valija         |

Hacé clic en **Cambiar** para abrir el selector de color.

### Precio de artículos

![Configuracion Precio](_media/Configuracion/Configuracion_Precio.png)

El campo **Precio de artículos** define el valor por defecto con el que se exportará a Open Orange (ej. `0.05`).

### Ingreso Open Orange — Mapeo de columnas

![Configuracion Open Orange](_media/Configuracion/Configuracion_Open_Orange.png)

Esta sección configura los **nombres de las columnas** del archivo que se enviará a Open Orange.  
Cada fila tiene el nombre interno del sistema y el nombre de columna destino editable.

| Campo interno     | Columna destino (editable) | Incluir |
| ----------------- | -------------------------- | ------- |
| Código            | ArtCode                    | ✅      |
| Unidades          | Qty                        | ✅      |
| Precio            | PriceSalesMan              | ✅      |
| Número de Serie   | SerialNr                   | ✅      |
| Fecha Vencimiento | ExpireDate                 | ✅      |
| Batch Status      | BatchStatus                | ☐       |
| Kit               | Kit                        | ✅      |

> [!INFO]
> El campo **Kit** sólo es relevante para valijas de AB. Si está habilitado, aparecerá el textBox de **Serie Procesador** en la tab Valija durante el Ingreso. Ver [Tab Valija en Ingresos](ingresos#tab-valija).

Hacé clic en **Guardar Cambios** (ícono de disquete) para confirmar.

---

## Configuración por Línea

Todas las líneas (excepto Bernafon) comparten el mismo esquema de configuración. Se pueden definir los nombres de columna para dos contextos:

- **Ingreso de Stock** — columnas del archivo de anexo al recibir mercadería.
- **Inventario** — columnas del archivo de stock exportado desde Open Orange.

<!-- PLACEHOLDER: Captura de Configuraciones Atos -->

![Configuracion Atos](_media/Configuracion/Configuracion_Atos.png)

**Ejemplo para Atos:**

| Contexto   | Campo         | Nombre de columna |
| ---------- | ------------- | ----------------- |
| Ingreso    | Código        | Modelo            |
| Ingreso    | Unidades      | Cantidad          |
| Ingreso    | Descripción   | Modelo            |
| Ingreso    | Núm. de Serie | Lote              |
| Ingreso    | Vencimiento   | Vencimiento       |
| Inventario | Código        | Articulo          |
| Inventario | Unidades      | Stock             |
| Inventario | Descripción   | Descripción       |
| Inventario | Núm. de Serie | Nro Serie         |
| Inventario | Vencimiento   | Fecha Vto.        |

> [!WARNING]
> Estos nombres deben coincidir **exactamente** con los encabezados del archivo de anexo. El sistema busca esos encabezados en las primeras **20 filas** del archivo al cargarlo.

---

## Configuración Bernafon

Bernafon tiene una sección adicional: **Movimiento de Stock**, que incluye:

- **Código** — nombre de la columna de código de artículo en el movimiento.
- **Unidades** — nombre de la columna de cantidad.
- **Códigos de Artículo** — lista de códigos que se desglosan automáticamente al importar un movimiento.

<!-- PLACEHOLDER: Captura de Configuraciones Bernafon -->

![Configuración Bernafon](_media/Configuracion/Configuracion_Bernafon.png)

Podés **exportar e importar** la lista de códigos con los botones **Exportar Datos** / **Importar Datos**.

> [!TIP]
> Si recibís un movimiento con un código que no está en esta lista, podés desglosarlo manualmente con doble clic. Ver [Movimientos Bernafon](movimientos-bernafon#desglosar-un-articulo).
