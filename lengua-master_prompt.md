
GENERAR ARCHIVOS COMPLETOS: LENGUA CASTELLANA Y LITERATURA - TODA LA ESO (1º a 4º)
Archivos a generar: 96 archivos HTML (48 temas × 2 archivos cada uno: Teoria + Ejercicios)
⚠️ INSTRUCCIÓN CRÍTICA: Genera TODOS los temas secuencialmente en esta respuesta. Usa delimitores claros entre cada archivo. Si se alcanza el límite de tokens, continúa automáticamente desde el último archivo sin reiniciar, manteniendo la estructura exacta.

═══════════════════════════════════════════════
🔧 ESPECIFICACIONES TÉCNICAS CRÍTICAS (OBLIGATORIAS)
═══════════════════════════════════════════════

✅ JAVASCRIPT - COMILLAS Y SINTAXIS:
• Usar SIEMPRE comillas simples '...' o SIEMPRE dobles "...", pero CONSISTENTES.
• Verificar que TODAS las comillas estén equilibradas.
• Ejemplo CORRECTO: `if(localStorage.getItem('theme') === 'dark')`

✅ KATEX - INICIALIZACIÓN SEGURA:
• Usar `ignoredTags` para evitar conflictos con SVG o scripts:
  ```javascript
  function initKaTeX() {
    if (typeof renderMathInElement !== 'function') return;
    try {
      renderMathInElement(document.body, {
        delimiters: [
          {left: "$$", right: "$$", display: true},
          {left: "$", right: "$", display: false}
        ],
        throwOnError: false,
        ignoredTags: ["svg", "script", "noscript", "style", "textarea", "pre", "code"]
      });
    } catch (e) { console.warn('KaTeX error:', e); }
  }
  ```

✅ CHART.JS - ESTRUCTURA OBLIGATORIA:
• SIEMPRE incluir `data: { ... }` como propiedad raíz.
• SIEMPRE usar `data: [...]` dentro de cada `dataset`.
• Ejemplo CORRECTO:
  ```javascript
  const ctx = document.getElementById('chart1').getContext('2d');
  new Chart(ctx, {
    type: 'bar',
    data: {
      labels: ['Sujeto', 'Verbo', 'CD', 'CI', 'CC'],
      datasets: [{
        label: 'Frecuencia sintáctica',
        data: [12, 15, 8, 5, 3],
        backgroundColor: '#e65100'
      }]
    },
    options: { responsive: true }
  });
  ```
• Al cambiar de tema: `if(chartInstance) chartInstance.destroy();` antes de recrear.

✅ ORDEN DE INICIALIZACIÓN (DOMContentLoaded):
1. KaTeX: `setTimeout(initKaTeX, 30);`
2. Chart.js: después de KaTeX o dentro del mismo timeout.
3. Al toggle oscuro: repetir orden exacto.

✅ VALIDACIÓN FINAL:
• [ ] Comillas equilibradas en JS.
• [ ] `data: { ... }` en todos los Chart.js.
• [ ] KaTeX con `ignoredTags`.
• [ ] CERO Mermaid en código o comentarios.
• [ ] Variables definidas, sin errores de consola.

═══════════════════════════════════════════════
📐 ARQUITECTURA DE LAYOUT (OBLIGATORIA)
═══════════════════════════════════════════════
• Header fijo: Título + toggle modo oscuro + icono FA.
• Sidebar navegación (desktop) / Menú hamburguesa (<992px).
• Área principal: `width: 100%; padding: 1.5rem; max-width: 1600px; margin: 0 auto;`
• Maquetación: 100% CSS Grid y Flexbox. Cero `<br>` para espaciado.
• Scrollspy (.active en sección visible) + `scroll-behavior: smooth`.
• Responsive: Sidebar → drawer móvil. Grid → 1fr móvil, 2-3fr desktop.

🎨 DISEÑO VISUAL Y UI:
• Color base Lengua: #e65100. Variables CSS en :root para light/dark.
• Modo oscuro: Toggle `<i class="fa-solid fa-moon"></i>`. Clase `.dark-mode` en `<body>`. Transición 0.3s.
• Tipografía: Albert Sans (Google Fonts). Fallback: system-ui, sans-serif.
• Iconos: Font Awesome 6.5. CERO emojis en UI.
• CSS puro, <400 líneas, bien comentado.

⚡ TECNOLOGÍAS (CDN OBLIGATORIOS):
• KaTeX: https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css + JS + auto-render
• Chart.js: https://cdn.jsdelivr.net/npm/chart.js
• Inicialización en DOMContentLoaded siguiendo orden especificado.

═══════════════════════════════════════════════
📖 CONTENIDO Y TONO (LENGUA)
═══════════════════════════════════════════════
• Tono: Académico, riguroso, técnico. Lenguaje preciso, orientado a la competencia lingüística real.
• Ejemplos: Textos periodísticos, fragmentos literarios reales, discursos públicos, redes sociales, ensayos académicos.
• Referencias culturales: Estratégicas y contextuales (máx 1-2 por tema). Ej: análisis de letras de rap para métrica, estructura de guiones de series para narrativa, discursos históricos para retórica, podcasts para registro oral.
• Estructura por subtema:
  1. Marco teórico claro y conciso
  2. Reglas o principios estructurados (tablas/listas HTML)
  3. Ejemplos analizados paso a paso
  4. Caja "Aplicación práctica" (comprensión, producción, análisis)
  5. Uso de KaTeX para esquemas retóricos, métricos o fórmulas sintácticas si procede
  6. Chart.js para visualización de frecuencias léxicas, estructuras textuales o evolución literaria

═══════════════════════════════════════════════
📝 ARCHIVO EJERCICIOS: GRID DE PRÁCTICA INTENSIVA
═══════════════════════════════════════════════
• Layout: `display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); gap: 1.2rem;`
• CANTIDAD MÍNIMA POR SUBTEMA:
  - Nivel Básico (⭐): 10 ejercicios
  - Nivel Intermedio (⭐⭐): 9 ejercicios
  - Nivel Avanzado (⭐⭐⭐): 6 ejercicios
  - TOTAL: 25 × 4 subtemas = 100 + 20 preguntas test = 120+ por tema
• Tipos de ejercicios: Análisis morfológico/sintáctico, corrección ortográfica, identificación de figuras retóricas, comprensión lectora, producción textual guiada, reescritura, debate estructurado, comentario de fragmentos.
• Estructura de tarjeta:
  ```html
  <div class="exercise-card">
    <div class="card-header"><i class="fa-solid fa-pen-fancy"></i> <span class="level">⭐⭐</span> <span class="code">T.X.Y.ZZ</span></div>
    <div class="card-body"><p>Enunciado preciso. Texto de referencia si es necesario.</p></div>
    <div class="answer-area"><textarea placeholder="Responde o analiza aquí..."></textarea><div class="lines-guide"></div></div>
  </div>
  ```
• ❌ SIN SOLUCIONARIO. SIN PISTAS. Instrucciones autocontenidas, progresión lógica, espacios amplios.

═══════════════════════════════════════════════
📦 SALIDA ESPERADA
═══════════════════════════════════════════════
1. Genera los 96 archivos HTML completos en esta respuesta, en orden estricto: 1ºESO_T1 → 1ºESO_T12, 2ºESO_T1 → 2ºESO_T12, 3ºESO_T1 → 3ºESO_T12, 4ºESO_T1 → 4ºESO_T12.
2. Usa delimitores claros: `<!-- INICIO: Lengua_XESO_TemaY_Teoria.html -->` y `<!-- FIN: ... -->`
3. Cada archivo debe ser autónomo: `<html>`, `<head>`, `<body>`, CSS/JS embebidos, CDNs cargados, inicialización correcta.
4. Verifica estrictamente todas las reglas técnicas antes de entregar.
5. NO añadas texto explicativo fuera de los bloques HTML. SOLO código.
6. Si se corta por límite de tokens, continúa automáticamente manteniendo la estructura exacta y sin reiniciar documentos.

Lista completa de temas a generar:
[Inserta aquí la estructura markdown de los 48 temas con sus 4 subtemas cada uno, tal como se proporcionó arriba]

Genera ahora.
