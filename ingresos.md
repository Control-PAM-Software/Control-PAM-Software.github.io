# Ingreso de Mercadería

El módulo de **Ingresos** se accede desde la barra de menú superior: **Ingreso → [Línea]**.

Si bien todas las ventanas de ingreso tienen el mismo formato base, pueden presentar pequeñas diferencias según la línea seleccionada. Todas comparten **tres tabs** en la parte inferior:

| Tab           | Función                                                           |
| ------------- | ----------------------------------------------------------------- |
| **Anexo**     | Muestra la tabla del anexo (mercadería esperada según el remito). |
| **Resultado** | Genera la tabla final para exportar a Open Orange.                |
| **Valija**    | Donde se cargan los artículos físicos recibidos.                  |

<!-- PLACEHOLDER: GIF del flujo completo de ingreso -->

![Ingreso](_media/Ingreso/Ingreso.png)

---

## Tab Anexo

Esta tab es el **punto de partida** del proceso de ingreso. Desde el submenú lateral izquierdo disponés de las siguientes acciones:

### Pegar Anexo

Copiá el contenido del anexo (incluyendo el encabezado de la tabla) y hacé clic en **Pegar Anexo**. El sistema detectará automáticamente las columnas configuradas.

También podés **arrastrar el archivo directamente** a la ventana (drag & drop). Esto funciona con **múltiples archivos a la vez** — todos se cargarán juntos.

> [!INFO]
> Al soltar el archivo, el sistema busca los encabezados configurados en las primeras **20 filas**. Si no los encuentra, verificá la configuración en [Configuración por Línea](configuracion#configuracion-por-linea).

<!-- PLACEHOLDER: GIF del drag & drop del anexo -->

![Drag and drop del anexo](_media/Ingreso/Ingreso_Valija_Drag_Drop.gif)

### Comparar

Una vez cargado el Anexo **y** los artículos físicos en la [Tab Valija](#tab-valija), hacé clic en **Comparar** para confrontar ambas listas.

El sistema resaltará las filas con los colores configurados:

- <span class="badge-hot">Color diferencias</span> — artículo encontrado pero con diferencias, ya sea en cantidad, número de serie o vencimiento.
- <span class="badge-warn">Color faltantes</span> — artículo del Anexo no encontrado en la Valija.

En cualquiera de los dos casos, el sistema indica el motivo de la diferencia. Para ello, coloque el cursor sobre la fila resaltada con color.

### Open Orange

Luego de comparar, hacé clic en **Open Orange** para generar la tabla de exportación. Esto prepara la información para la [Tab Resultado](#tab-resultado).

### Limpiar

Borra toda la información cargada en esta tab. No afecta a las otras tabs.

### Serie Procesador _(solo AB con Kit habilitado)_

Si en **Configuración → Ingreso Open Orange** la opción **Kit** está activa, aparece un campo en la parte superior derecha para ingresar el número de serie del procesador de la valija. Este valor se incluye en la exportación a Open Orange.

---

## Tab Resultado

Muestra la **tabla final** que se usará para el ingreso en Open Orange.

<!-- PLACEHOLDER: Captura de Tab Resultado con datos -->

![Tab Resultado](_media/Ingreso/Ingreso_Tab_Resultado.png)

Acciones disponibles:

- **Copiar Tabla** — copia al portapapeles, listo para pegar en Open Orange.
- **Acciones ▲** — menú desplegable:
  - **Imprimir** — envía la tabla a impresora.
  - **Excel** — exporta como archivo `.xlsx`.
- **Limpiar** — vacía la tabla del resultado.

---

## Tab Valija

Es donde se registran los **artículos físicos recibidos**. Podés cargarlos de dos formas:

![Tab Recibido](_media/Ingreso/Ingreso_Tab_Recibido.png)

### Pickeo con lectora (modo normal)

1. Hacé clic en el textBox **Código** para enfocar el cursor.
2. Leé el código de barras o QR del artículo con la lectora.
3. Dependiendo de la línea, se leerá también el **Número de Serie** (AB tiene 2 campos; Atos tiene 1 campo unificado).
4. El sistema completa la tabla dinámicamente a medida que pickeás.

<!-- PLACEHOLDER: GIF del pickeo con lectora -->

![Tab Recibido](_media/Ingreso/Ingreso_Tab_Recibido_Picking.png)

### Artículo Manual

Para cargar artículos sin lectora, o para ingresar muchas unidades de un mismo artículo. Ver [Artículo Manual](#articulo-manual).

### Tiene Pila _(solo AB)_

Agrega automáticamente un artículo de pila con datos predefinidos:

| Campo           | Valor      |
| --------------- | ---------- |
| Código          | `070-0329` |
| Número de serie | `150650`   |

### Acciones ▲

- **Imprimir** — imprime el contenido de la Valija.
- **Excel** — exporta como `.xlsx`.
- **Generar QR** — genera un código QR con toda la información de la valija para pickeo posterior. Ver [Generación de QR](#generacion-de-qr).

---

## Generación de QR _(solo Valijas de AB)_

Desde la [Tab Valija](#tab-valija), en **Acciones ▲ → Generar QR** se abre el **Generador de Códigos QR**.

<!-- PLACEHOLDER: Captura del diálogo Generar QR para Valija -->

![Generador de QR](_media/Ingreso/Ingreso_Tab_Recibido_Qr.png)

Los campos disponibles son:

| Campo                    | Descripción                                                  | Obligatorio |
| ------------------------ | ------------------------------------------------------------ | ----------- |
| **Nombre**               | Nombre del paciente                                          | No          |
| **Apellido**             | Apellido del paciente                                        | No          |
| **Serie del Procesador** | Se autocompleta con el Nro. de Serie de la fila seleccionada | No          |

> [!TIP]
> El campo **Serie del Procesador** se autocompleta automáticamente con el número de serie de la fila que estaba seleccionada en la tabla al momento de abrir la ventana.

Hacé clic en **GENERAR QR** para continuar. El sistema pedirá opciones de impresión y mostrará una **vista previa** con:

- Nombre del paciente (PACIENTE: **JUAN PEREZ**)
- Número de serie
- Código QR escaneable

En la vista previa, hacé clic en el **ícono de impresora** (primer ícono de la barra) para imprimir.

---

## Artículo Manual

Se abre desde la [Tab Valija](#tab-valija) con el botón **Artículo Manual** del submenú lateral.

<!-- PLACEHOLDER: Captura de la ventana Artículo Manual -->

![Ventana Artículo Manual](_media/Ingreso/Ingreso_Tab_Recibido_Articulo_Manual.png)

La ventana tiene dos secciones:

### Ingreso por lectora

| Campo                 | Descripción                                           |
| --------------------- | ----------------------------------------------------- |
| **Código Barra / QR** | Leer con lectora (decodifica automáticamente)         |
| **Número de Serie**   | Campo adicional para líneas que lo requieren (ej. AB) |

> Para Atos, aparece un único campo unificado.

### Ingreso manual

| Campo           | Descripción                         |
| --------------- | ----------------------------------- |
| **Código**      | Código del artículo                 |
| **Serie**       | Número de serie                     |
| **Vencimiento** | Fecha de vencimiento (`dd/mm/aaaa`) |
| **Cantidad**    | Unidades a ingresar                 |

Confirmá con ✔ o cancelá con ✗.

**Casos de uso habituales:**

- Ingresar **muchas unidades** de un mismo artículo: leés el código una vez y modificás la cantidad manualmente.
- Registrar una **caja con contenido parcial** sin tener que pickear unidad por unidad.
