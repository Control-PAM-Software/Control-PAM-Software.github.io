# Control — Sistema de Gestión de Inventario

<div class="ad-hero">
  <p>Manual de usuario del sistema <strong>Control</strong> desarrollado para <strong>PAM Argentina</strong>: ingreso de mercadería, comparación contra anexos, exportación a Open Orange e inventarios físicos.</p>
  <div class="ad-chips">
    <span class="ad-chip">📦 3 módulos</span>
    <span class="ad-chip">🏭 5 líneas</span>
    <span class="ad-chip">💻 .NET 8.0 · WinForms</span>
  </div>
</div>

---

## ¿Qué hace Control?

Control es una aplicación de escritorio (.NET 8.0 / WinForms) que centraliza tres flujos operativos clave:

<div class="ad-grid">
  <div class="ad-card"><span class="ad-icon">📥</span><span class="ad-label">Ingresos</span><span class="ad-value">Carga y comparación de mercadería recibida contra el anexo esperado</span></div>
  <div class="ad-card"><span class="ad-icon">📦</span><span class="ad-label">Inventario</span><span class="ad-value">Conteo físico de stock con descuento en tiempo real</span></div>
  <div class="ad-card"><span class="ad-icon">🔄</span><span class="ad-label">Movimientos Bernafon</span><span class="ad-value">Desglose de artículos de stock específico de Bernafon</span></div>
</div>

---

## Flujo general de trabajo

<!--
  PLACEHOLDER GIF: Reemplazar la línea de abajo con el GIF del flujo completo
  Ejemplo: ![Flujo completo](assets/gifs/flujo-general.gif)
-->

![Pantalla Principal](_media/Pantalla_Principal.png)

El flujo típico de un **Ingreso de Mercadería** sigue estos pasos:

1. **Cargar el Anexo** — Pegarlo desde el portapapeles o arrastrar el archivo al sistema.
2. **Pickear la Valija** — Leer los artículos físicos con lectora de código de barras/QR.
3. **Comparar** — El sistema detecta diferencias y faltantes automáticamente.
4. **Exportar a Open Orange** — Generar la tabla final y copiarla al portapapeles.
5. **Exportar Etiquetas** — Generar el Excel de etiquetas del despacho. Ver [Exportar Etiquetas](ingresos#exportar-etiquetas).

---

## Navegación del manual

Usá la barra lateral izquierda para navegar entre módulos. También podés usar el **buscador** en la parte superior de la barra lateral.

> [!TIP]
> Los términos subrayados en azul son **enlaces internos** — hacé clic para ir directamente a esa sección.

---

## Convenciones de este manual

| Elemento    | Significado                               |
| ----------- | ----------------------------------------- |
| `Código`    | Texto que aparece tal cual en la interfaz |
| **Negrita** | Acción importante o botón clave           |
| →           | Secuencia de navegación en el menú        |
| `070-0329`  | Valor de ejemplo o código de artículo     |

---

_Para más información acerca de la aplicación ver sección [Acerca De](acerca_de.md)_
