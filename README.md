# Accesibilidad y Copilot (WCAG 2.2 AA)

## Español

### 1. Objetivo
Este proyecto documenta el uso de asistentes de programación (Copilot/Gemini) para corregir una miniweb y llevarla a cumplimiento de accesibilidad **WCAG 2.2 nivel AA** (AAA opcional), validando resultados con varias herramientas.

### 2. Estructura del repositorio
- `original/`: versión inicial con errores de accesibilidad (base de pruebas).
- `corregido/`: versión corregida tras aplicar el prompt.
- `prompts/promt1`: prompt utilizado para la corrección.
- `evidencias/wave/antes` y `evidencias/wave/despues`: capturas WAVE.
- `evidencias/axe/antes` y `evidencias/axe/despues`: capturas Axe.
- `evidencias/lighthouse/`: capturas Lighthouse (antes y después).

### 3. Páginas evaluadas
- `index.html`
- `formulario.html`
- `tabla.html`
- `media.html`

### 4. Prompt usado
Prompt aplicado en el asistente:

```txt
Revisa y corrige este proyecto HTML/CSS para que cumpla WCAG 2.2 nivel AA.

Objetivo:
- Mejorar accesibilidad sin cambiar la funcionalidad principal.

Aplica estos cambios:
1. Estructura semántica correcta: header, nav, main, section, footer.
2. Añadir lang="es" en <html> y mantener metadatos correctos.
3. Corregir jerarquía de encabezados (h1 único y orden lógico h2, h3...).
4. Formularios accesibles:
   - label asociado a cada campo (for/id correctos)
   - mensajes y ayudas con aria-describedby cuando sea necesario
   - eliminar tabindex positivos y dejar orden natural de tabulación
5. Enlaces y botones:
   - textos descriptivos (evitar “haz clic aquí”)
   - eliminar enlaces vacíos
6. Tabla accesible:
   - usar caption
   - usar th con scope para encabezados
   - quitar role incorrectos como role="presentation" si es tabla de datos
7. Imágenes y media:
   - alt descriptivo en imágenes informativas
   - quitar autoplay en audio/video si afecta accesibilidad
8. Contraste y foco:
   - ajustar colores para contraste AA (texto normal mínimo 4.5:1)
   - asegurar foco visible en elementos interactivos
9. Navegación por teclado:
   - mantener skip link funcional apuntando a un id existente
   - asegurar navegación completa con teclado

Entrega:
- Devuélveme el código corregido completo por archivo (HTML y CSS).
- Incluye un resumen corto de los cambios realizados para WCAG 2.2 AA.
```

### 5. Proceso de validación
1. Se preparó una versión inicial (`original/`) con fallos de contraste, estructura semántica, jerarquía de encabezados, formularios, tabla, media y navegación por teclado.
2. Se ejecutaron validaciones **antes** con:
   - WAVE
   - Axe DevTools
   - Lighthouse
3. Se aplicó el prompt en la versión `corregido/`.
4. Se volvieron a ejecutar validaciones **después** con las mismas herramientas.
5. Se compararon resultados y se guardaron capturas.

### 6. Problemas encontrados y solución aplicada
- Problema: falta de semántica y landmarks.
  Solución: uso de `header`, `nav`, `main`, `section`, `footer` y jerarquía correcta de títulos.
- Problema: contraste insuficiente y foco no visible.
  Solución: actualización de paleta y estilos de foco visible.
- Problema: formularios no accesibles.
  Solución: asociación correcta `label` + `for/id`, orden de tabulación natural y eliminación de `tabindex` positivos.
- Problema: tabla de datos mal estructurada.
  Solución: inclusión de `caption`, `th` y `scope`; retirada de roles incorrectos.
- Problema: enlaces ambiguos y media sin atributos adecuados.
  Solución: textos de enlace descriptivos, eliminación de enlaces vacíos, `alt` en imágenes y ajuste de reproducción multimedia.

### 7. Resultados (antes vs después)
Las validaciones muestran una mejora clara entre la versión `original/` y la versión `corregido/`, reduciendo errores de accesibilidad y elevando el nivel de cumplimiento hacia WCAG 2.2 AA en las páginas analizadas.

### 8. Evidencias
- WAVE antes: `evidencias/wave/antes`
- WAVE después: `evidencias/wave/despues`
- Axe antes: `evidencias/axe/antes`
- Axe después: `evidencias/axe/despues`
- Lighthouse: `evidencias/lighthouse`

### 9. Conclusión
El proyecto demuestra un flujo completo de mejora de accesibilidad asistida por IA: análisis inicial, prompt de corrección, validación iterativa y evidencia comparativa. El resultado final está orientado al cumplimiento de **WCAG 2.2 AA**.

---

## English

### 1. Goal
This project documents how coding assistants (Copilot/Gemini) were used to fix a small website and move it toward **WCAG 2.2 AA** accessibility compliance (AAA optional), validated with multiple tools.

### 2. Repository structure
- `original/`: initial version with accessibility issues (test baseline).
- `corregido/`: fixed version after applying the prompt.
- `prompts/promt1`: prompt used for correction.
- `evidencias/wave/antes` and `evidencias/wave/despues`: WAVE screenshots.
- `evidencias/axe/antes` and `evidencias/axe/despues`: Axe screenshots.
- `evidencias/lighthouse/`: Lighthouse screenshots (before/after).

### 3. Evaluated pages
- `index.html`
- `formulario.html`
- `tabla.html`
- `media.html`

### 4. Prompt used
The same prompt shown in the Spanish section (`prompts/promt1`) was used as the base instruction for the assistant.

### 5. Validation process
1. An initial version (`original/`) was prepared with issues in contrast, semantic structure, heading order, forms, tables, media, and keyboard navigation.
2. **Before** validation was executed with:
   - WAVE
   - Axe DevTools
   - Lighthouse
3. The prompt was applied to the `corregido/` version.
4. **After** validation was executed again with the same tools.
5. Results were compared and screenshots were stored.

### 6. Issues found and applied fixes
- Issue: missing semantic landmarks.
  Fix: proper use of `header`, `nav`, `main`, `section`, `footer`, and heading hierarchy.
- Issue: low contrast and missing visible focus.
  Fix: updated color palette and visible focus styles.
- Issue: inaccessible forms.
  Fix: correct `label` + `for/id` mapping, natural tab order, and removal of positive `tabindex`.
- Issue: incorrect data table structure.
  Fix: added `caption`, `th`, `scope`, and removed incorrect roles.
- Issue: ambiguous links and incomplete media accessibility.
  Fix: descriptive link text, removed empty links, added image `alt`, and adjusted media playback behavior.

### 7. Results (before vs after)
Validation reports show a clear improvement from `original/` to `corregido/`, reducing accessibility errors and moving the project toward WCAG 2.2 AA compliance across the evaluated pages.

### 8. Evidence
- WAVE before: `evidencias/wave/antes`
- WAVE after: `evidencias/wave/despues`
- Axe before: `evidencias/axe/antes`
- Axe after: `evidencias/axe/despues`
- Lighthouse: `evidencias/lighthouse`

### 9. Conclusion
This project shows a full AI-assisted accessibility workflow: baseline analysis, correction prompt, iterative validation, and comparative evidence. The final result is oriented to **WCAG 2.2 AA** compliance.




## URL de acceso web
- .\tarea\Accesibilidad y Copilot\corregido: https://accesibilidad-corregido.web.app
- Alternativa FirebaseApp: https://accesibilidad-corregido.firebaseapp.com
- .\tarea\Accesibilidad y Copilot\original: https://accesibilidad-original.web.app
- Alternativa FirebaseApp: https://accesibilidad-original.firebaseapp.com

