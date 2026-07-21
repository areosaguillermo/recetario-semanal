# Personas configurables por comida + deploy en GitHub Pages

Fecha: 2026-07-20 · Estado: aprobado

## Contexto
App de una sola página (`index.html`, antes `recetario-app.html`): menú semanal, lista de compras autogenerada, banco de recetas y recetario imprimible. Datos embebidos en el objeto `DATA` (recetas y plan semanal).

## Requerimientos aprobados
1. **Personas configurables por comida**: control «– N +» (1 a 8) por almuerzo/cena de cada día, junto al selector de receta.
2. **Escalado real de cantidades**: los ingredientes pasan de texto libre a dato numérico (`num`, `unidad`, `nota`); los "a gusto"/"opcional" no se escalan. Cada receta declara `rinde` (porciones base). Factor = personas / rinde, con formato amigable (1200 g → "1,2 kg", redondeo de unidades enteras como huevos).
3. **Recetas base reutilizables** (pollo desmenuzado, boloñesa): se escalan según la demanda total de la semana (suma de personas de las comidas que las usan, vía `usaBase`).
4. **Lista de compras exacta**: suma numérica real de cantidades entre recetas (reemplaza la concatenación "500 g + 700 g"), respetando escalado. El recetario imprimible refleja cantidades escaladas y personas por comida.
5. **Persistencia**: menú y personas en `localStorage`, con botón «↩️ Restablecer semana original».
6. **Deploy**: repo público `recetario-semanal` en la cuenta areosaguillermo, GitHub Pages activo → https://areosaguillermo.github.io/recetario-semanal/

## Decisiones
- El modal de receta muestra cantidades escaladas a la demanda del plan si la receta está en la semana; si no, las cantidades base.
- Los ingredientes de rubro `reuso` no van a la lista de compras (comportamiento actual, se mantiene).
- Sin build ni dependencias: sigue siendo un único HTML autocontenido.
