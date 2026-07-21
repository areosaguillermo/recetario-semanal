# 🍳 Recetario semanal

App web para organizar las comidas de la semana: menú de lunes a viernes, banco de recetas, lista de compras generada automáticamente (ordenada por sector del súper) y recetario imprimible para la cocinera.

**➡️ Ver online:** https://areosaguillermo.github.io/recetario-semanal/

## Funcionalidades

- 📅 **Menú semanal editable**: cambiá cualquier almuerzo o cena con el selector.
- 👥 **Personas configurables por comida** (1 a 8): las cantidades de cada receta y la lista de compras se escalan automáticamente. Las preparaciones base (pollo desmenuzado, boloñesa, milanesas) se dimensionan según la demanda total de la semana.
- 🛒 **Lista de compras exacta**: suma real de cantidades entre recetas, con checklist y botón para copiar.
- 📖 **Banco de recetas** con búsqueda y filtros.
- 🖨️ **Recetario imprimible** (menú, orden de cocina, compras y recetas paso a paso).
- 💾 Los cambios se guardan en el navegador (localStorage), con botón para restablecer la semana original.

## Estructura

- `index.html` — toda la app, sin dependencias ni build.
- `Recetario-Semana-1.pdf` — versión PDF de la semana 1.
