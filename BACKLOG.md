# 📋 Backlog de Producto y Calidad Pedagógica: DeutschPath / DeutschMeister

> **Visión**: Crear la plataforma web definitiva de aprendizaje de alemán para hispanohablantes, combinando la **gamificación táctil y adictiva de Duolingo** (botones 3D, rachas, feedback sonoro, XP, Word Tiles) con el **rigor conceptual de Babbel** (fórmulas sintácticas, matrices de casos, explicaciones gramaticales contrastadas y preparación para exámenes oficiales MCER Goethe/telc).

---

## 🚦 Matriz de Prioridades

- **🔴 P0 (Crítico / Inmediato)**: Carencias funcionales que frenan la experiencia de aprendizaje o el andamiaje didáctico básico.
- **🟡 P1 (Alta / Siguiente Sprint)**: Herramientas interactivas clave que elevan la retención y la autonomía del estudiante.
- **🟢 P2 (Medio Plazo / Diferenciadores)**: Simuladores avanzados, preparación formal de exámenes y módulos fonéticos.
- **⚪ P3 (Futuro / Nice to have)**: PWA, sincronización remota y expansión a B2/C1.

---

## 🗺️ Mapa de Épicas

```mermaid
graph TD
    A[DeutschPath Roadmap] --> B[Épica 1: Diagnóstico y Onboarding]
    A --> C[Épica 2: Profundidad de Lecciones, Vocabulario y Comprensión Lectora]
    A --> D[Épica 3: Gimnasio de Declinaciones Interactivo]
    A --> E[Épica 4: Integración del Buscador de Verbos]
    A --> F[Épica 5: Roleplays y Simulaciones Reales]
    A --> G[Épica 6: Fonética y Nemotécnicas Especiales]
    A --> H[Épica 7: Preparación de Exámenes y Expansión B2]
```

---

## 🔴 P0 — Crítico e Inmediato

### [EP1-01] Test de Diagnóstico Rápido de Nivel (*Schnelltest*)
- **Área**: Onboarding / UX
- **Nivel**: Global (A1 / A2 / B1)
- **Problema actual**: El alumno nuevo entra a la web y no sabe si empezar en A1, A2 o B1, ni en qué estación concreta situarse.
- **Descripción**: Modal interactivo accesible desde la cabecera ("¿Cuál es mi nivel? 🎯") con un test adaptativo de 5 preguntas rápidas:
  1. Pregunta 1 (A1 básico): Saludo y regla V2 (*Heute ___ ich in Berlin*).
  2. Pregunta 2 (A1 intermedio): Acusativo masculino (*Ich habe ___ Hund*).
  3. Pregunta 3 (A2 inicial): Subordinada con *weil* (posición final del verbo).
  4. Pregunta 4 (A2 consolidado): *Wechselpräpositionen* (contraste Wo? vs Wohin?).
  5. Pregunta 5 (B1): Pasiva con *werden* o cláusula de infinitivo con *zu*.
- **Criterio de Aceptación (DoD)**:
  - Al terminar, muestra el nivel recomendado y desbloquea/posiciona automáticamente al alumno en la estación óptima.
  - Ofrece botón de "Aceptar sugerencia" o "Explorar por mi cuenta".

---

### [EP2-01] Ampliación del Andamio de Práctica (Paso 3 de cada Estación)
- **Área**: Didáctica / Contenidos
- **Nivel**: A1, A2, B1
- **Problema actual**: Cada estación cuenta únicamente con **1 ejercicio** en la fase de Práctica antes de saltar directamente al examen final.
- **Descripción**: Ampliar el array `practice` de cada unidad de A1, A2 y B1 para que contenga **3 a 4 ejercicios progresivos**:
  - Ejercicio 1: Reconocimiento básico de la regla.
  - Ejercicio 2: Selección entre distractores típicos de hispanohablantes.
  - Ejercicio 3: Transformación o aplicación en frase completa.
- **Criterio de Aceptación (DoD)**:
  - Todas las estaciones de A1, A2 y B1 tienen al menos 3 ejercicios interactivos con su explicación pedagógica `why`.
  - El botón "Continuar al Examen" solo se desbloquea tras responder todos los micro-retos.

---

### [EP2-03] Módulo de Textos de Comprensión Lectora Extensa (*Leseverstehen*) en cada Sección
- **Área**: Comprensión Lectora (*Leseverstehen*) / Didáctica / Preparación Goethe & telc
- **Nivel**: Global (A1, A2, B1 — 10 estaciones por nivel, 30 lecturas completas)
- **Problema actual**: El estudiante pasa de vocabulario y micro-práctica directamente a preguntas cortas aisladas tipo test. Carece de inmersión en lecturas continuas y realistas donde contextualizar la gramática y entrenar la lectura analítica requerida en los exámenes oficiales (*Leseverstehen Teil 1, 2 y 3* del Goethe-Zertifikat / telc).
- **Descripción**:
  - **Requisito de Extensión y Estructura**:
    * Cada estación debe incorporar un texto narrativo o documental en alemán auténtico de **al menos 3 a 5 párrafos ricos o muchos más** (entre 180 y 350+ palabras según el nivel), organizado en párrafos temáticos delimitados (*Absatz 1, Absatz 2, Absatz 3...*).
    * Temáticas adaptadas al contexto cultural germano de la estación: vida diaria en una WG en Berlín, anécdotas de trabajo en Siemens, correspondencia con la administración pública (*Bürgeramt*), viajes en Deutsche Bahn, etc.
  - **Batería de Preguntas de Comprensión Lectora (4 a 6 preguntas por texto)**:
    1. **Comprensión Global (*Globales Verstehen*)**: Identificación de la idea principal o la postura del autor.
    2. **Comprensión Selectiva / De detalle (*Detailliertes Verstehen*)**: Preguntas de opción múltiple (A, B, C) con localización de datos explícitos en un párrafo concreto.
    3. **Verdadero o Falso (*Richtig oder Falsch?*)**: Validación de afirmaciones contrastando con el texto.
    4. **Inferencia y Léxico en contexto**: Deducir el significado de una expresión a partir del contexto del párrafo.
  - **Soporte Didáctico y Audio**:
    * **Reproducción de Audio TTS**: Botón de escucha para el texto completo y por párrafo individual con voz nativa alemana (`de-DE`) para entrenar comprensión auditiva y lectora combinada (*Hör-Leseverstehen*).
    * **Glosario contextual**: Palabras clave y giros idiomáticos con traducción accesible en hover/tooltip.
    * **Feedback Inmediato y Razonado (`why`)**: Cada opción de respuesta explica de forma pedagógica el porqué del acierto o del fallo, citando la línea o párrafo del texto.
  - **Esquema de Datos Propuesto en `data/*.json`**:
    * Nuevo nodo `reading` en cada unidad de `data/a1.json`, `data/a2.json` y `data/b1.json`:
      ```json
      "reading": {
        "title": "Ein ganz normaler Tag in Berlin",
        "subtitle": "Daniel berichtet über seinen Alltag und seine WG",
        "paragraphs": [
          "Párrafo 1 (Introducción y contexto)...",
          "Párrafo 2 (Desarrollo y rutina diaria)...",
          "Párrafo 3 (Anécdota o conflicto comunicativo)...",
          "Párrafo 4 (Reflexión y conclusión)..."
        ],
        "glossary": [
          { "de": "die WG (Wohngemeinschaft)", "es": "piso compartido" }
        ],
        "questions": [
          {
            "type": "multiple_choice",
            "q": "¿Por qué decidió Daniel levantarse más temprano de lo habitual?",
            "options": ["Tenía una reunión importante", "Perdió el despertador", "Iba al supermercado"],
            "correct": 0,
            "why": "En el párrafo 2 se indica textualmente: 'Weil er um 8:00 Uhr ein wichtiges Meeting hatte...'"
          }
        ]
      }
      ```
- **Criterio de Aceptación (DoD)**:
  - 100% de las estaciones (A1, A2, B1) cuentan con su texto de lectura de 3 o más párrafos completos y extensos.
  - Cada lectura cuenta con un mínimo de 4 a 6 preguntas de comprensión con su respectiva justificación pedagógica `why`.
  - Paso interactivo dedicado en la interfaz de la estación (`Paso: Lectura y Comprensión`) previo al examen final.
  - Audio TTS funcional por párrafo y para el texto completo.
  - Integración en la gamificación (+25 XP por superar la lectura).

---

### [EP4-01] Integración del Buscador y Conjugador de Verbos (`verbs.json`) — ✅ COMPLETADA
- **Área**: Herramientas / UI
- **Nivel**: Global (A1, A2, B1)
- **Estado**: **Completada e Integrada en producción** en `index.html` y `data/verbs.json`.
- **Implementación realizada**:
  - Banco de **65 verbos fundamentales** en [data/verbs.json](file:///Users/dancach/Documents/proyectos/antigravity%20-%20deuschtmeinster/data/verbs.json) (con fallback reactivo `FALLBACK_VERBS` integrado en el bundle para total resiliencia offline).
  - **Buscador predictivo en tiempo real** por infinitivo en alemán, traducción al español, pretérito o participio II.
  - **Filtros combinados multidimensionales**:
    * Por Nivel: 🟢 A1, 🔵 A2, 🟣 B1.
    * Por Tipo gramatical y Régimen: 🚀 Auxiliar *SEIN* (`ist`), 🧲 Rigen Dativo, 🧱 Verbos modales, ✂️ Separables (*trennbare Verben*), 🪞 Reflexivos, 📍 Posición (*Wo/Wohin*).
  - **Tarjetas 3D Duolingo-style** con:
    * Botón de pronunciación acústica nativa (`SpeechSynthesisUtterance` con voz `de-DE`).
    * Matriz de las **3 Stammformen**: Präsens (er/sie), Präteritum y Partizip II con código de colores sintácticos.
    * Indicador de auxiliar (*ist* vs *hat*) con distintivo visual esmeralda/azul.
    * Régimen de caso obligatorio (Dativo, Acusativo o Preposicional).
    * Oración de ejemplo bilingüe de la vida real con botón de audio individual.
  - **Acceso universal sin fricción**: Disponible en 1 clic desde el botón ⚡ *Verbos* del header y desde la pestaña de la Chuleta Gramatical sin perder el avance de la lección en curso.

---

## 🟡 P1 — Alta Prioridad (Siguiente Sprint)

### [EP3-01] Gimnasio de Declinaciones Interactivo (*Deklinations-Trainer*) — ✅ COMPLETADA
- **Área**: Gramática Interactiva
- **Nivel**: A1, A2, B1
- **Estado**: **Completada e Integrada en producción** en `index.html` y `data/deklination.json`.
- **Implementación realizada**:
  - Banco de **30 retos interactivos** en [data/deklination.json](file:///Users/dancach/Documents/proyectos/antigravity%20-%20deuschtmeinster/data/deklination.json) cubriendo:
    * 🎯 Nominativ vs Akkusativ (El masculino rebelde: *den/einen/keinen/mich*).
    * 🧲 Verbos & Preposiciones de Dativo (*helfen, danken, gehören, schmecken, mit, bei, nach, zu, mir/dir*).
    * 📍 Wechselpräpositionen (*¿Wo? Dativ vs ¿Wohin? Akkusativ* con *stellen/stehen, legen/liegen, hängen, in/auf/an*).
    * 👑 Genitiv y N-Deklination (*des/der, wegen, während, trotz, statt, dem Kollegen*).
  - Selector de sub-vistas: 🥊 **Entrenador Interactivo** vs 📖 **Tablas de Referencia**.
  - Gamificación activa: Contador de racha 🔥 `streak` con animación de fuego, récord personal 🏆 y total de éxitos ⚡ (+10 XP por acierto).
  - Pastillas 3D estilo Duolingo con feedback acústico (`AudioFX.success() / AudioFX.error()`), explicaciones pedagógicas detalladas de la regla y audio nativo de la frase modelo.
  - Tablas completas actualizadas en la vista de referencia con los 4 casos (Nominativ, Akkusativ, Dativ y Genitiv) y pronombres personales.

---

### [EP2-02] Expansión Léxica y Modo Flashcards con Audio
- **Área**: Vocabulario / Retención
- **Nivel**: A1, A2, B1
- **Problema actual**: 4 palabras por unidad es un número reducido frente al estándar del MCER (600 palabras en A1, 1.200 en A2).
- **Descripción**:
  - Ampliar a 8–10 términos clave por estación en los JSON.
  - Implementar en el paso 2 de cada lección un conmutador: **"Modo Tarjetas"** (Flippable Flashcards) y **"Modo Lista Rápida"**.
  - Código de colores visual innegociable:
    - Azul para masculinos (`der`).
    - Rojo para femeninos (`die`).
    - Verde para neutros (`das`).
    - Amarillo para plurales.
- **Criterio de Aceptación (DoD)**:
  - 100% de sustantivos mostrados con su artículo, plural y audio funcional.

---

### [EP5-01] Simulador de Diálogos y Roleplays Guiados (*Rollenspiel Trainer*)
- **Área**: Expresión Oral / Diálogos
- **Nivel**: A1, A2, B1
- **Problema actual**: La pestaña de supervivencia solo tiene 1 pregunta interactiva aislada en una cafetería.
- **Descripción**: Crear 4 escenarios interactivos ramificados por turnos estilo chat:
  1. *Beim Bäcker* (Comprar panecillos y pedir precio).
  2. *Am Bahnhof* (Comprar billete de tren, preguntar por andén y retrasos).
  3. *Beim Arzt* (Describir dolor, pedir cita y receta en la farmacia).
  4. *Im Vorstellungsgespräch* (Presentación profesional formal para B1).
  - El interlocutor virtual habla (audio en alemán) y el alumno elige entre 3 respuestas posibles (1 adecuada, 1 demasiado informal, 1 gramaticalmente incorrecta).
- **Criterio de Aceptación (DoD)**:
  - Cada diálogo tiene entre 3 y 5 intercambios comunicativos con puntuación final y feedback del profesor.

---

## 🟢 P2 — Medio Plazo (Diferenciadores Pedagógicos)

### [EP6-01] Entrenador de Fonética y Pronunciación para Hispanohablantes
- **Área**: Fonética / Audio
- **Nivel**: A1 - B1
- **Descripción**: Módulo dedicado a desmitificar los sonidos del alemán que no existen en español:
  - La diéresis: Contraste de vocales `u` vs `ü`, `o` vs `ö`, `a` vs `ä`.
  - La consonante `z` como [ts] (*Zug, Zeit, zusammen*).
  - La `v` que suena a [f] (*Vogel, viel*) vs la `w` que suena a [v] (*Wasser, wohnen*).
  - El sonido de la `ch`: *ich-Laut* (suave tras e/i/ä/ö/ü) vs *ach-Laut* (fuerte tras a/o/u).
  - Ejemplos audibles comparativos y trucos musculares de articulación ("Pon boca de 'U' y di 'I' para decir 'Ü'").
- **Criterio de Aceptación (DoD)**:
  - Sección interactiva en el cuaderno de gramática con reproducción de audio para cada pareja mínima contrastada.

---

### [EP6-02] Píldoras Nemotécnicas: La Regla TE-KA-MO-LO y Falsos Amigos
- **Área**: Gramática / Estilística
- **Nivel**: A2 - B1
- **Descripción**:
  - **TE-KA-MO-LO Trainer**: Visualizador interactivo que permite al alumno arrastrar complementos para ordenar la frase en el orden canónico alemán: **TE**mporal -> **KA**usal -> **MO**dal -> **LO**kal.
  - **Muro de Falsos Amigos (*Falsche Freunde*)**: Tarjetas interactivas con trampas clásicas (*bekommen* = recibir, no llegar a ser; *also* = por tanto, no también; *der Chef* = jefe, no cocinero; *die Hochschule* = universidad, no escuela secundaria).
- **Criterio de Aceptación (DoD)**:
  - Retos específicos de Word Tiles donde se ponga a prueba el orden TE-KA-MO-LO.

---

### [EP7-01] Taller de Redacción y Expresión Escrita B1 (*Schreib-Werkstatt*)
- **Área**: Preparación de Exámenes (Goethe / telc)
- **Nivel**: B1
- **Descripción**: Plantillas y estructuras estándar para la prueba escrita de B1:
  - Cómo empezar y despedir una carta/email formal (*Sehr geehrte Damen und Herren... Mit freundlichen Grüßen*) vs informal (*Liebe Maria... Viele Grüße*).
  - Conectores de argumentación: *Einerseits... andererseits*, *Meiner Meinung nach*, *Aus diesem Grund*.
  - Ejercicios interactivos de rellenar conectores en modelos reales de cartas de reclamación o solicitud de información.
- **Criterio de Aceptación (DoD)**:
  - 3 modelos completos de redacción interactiva con checklist de autoevaluación.

---

## ⚪ P3 — Futuro y Arquitectura Técnica

### [EP8-01] Soporte PWA y Modo Offline Completo
- **Área**: Infraestructura Web
- **Descripción**: Configuración de `manifest.json` y Service Worker para instalar la plataforma como aplicación de escritorio o móvil (iOS/Android) con precacheo de audios y currículos JSON para estudiar en el avión o metro sin conexión.

### [EP8-02] Expansión a Nivel B2 (Competencia Operativa y Fluidez)
- **Área**: Contenidos Curriculares
- **Descripción**: Creación de `data/b2.json` con las 10 estaciones oficiales de B2: conectores dobles (*je... desto*, *nicht nur... sondern auch*), estilo indirecto con *Konjunktiv I*, participios atributivos ampliados y combinaciones verbo-nombre (*Nomen-Verb-Verbindungen*).

---

## 📊 Resumen Ejecutivo del Backlog

| Épica / Item | Título | Nivel | Prioridad | Esfuerzo | Impacto Alumno |
| :--- | :--- | :---: | :---: | :---: | :---: |
| **EP1-01** | Schnelltest (Test diagnóstico de nivel) | Global | 🔴 P0 | Bajo | 🔥🔥🔥 Muy Alto |
| **EP2-01** | Ampliación de Práctica (3-4 micro-retos/unidad) | A1-B1 | 🔴 P0 | Medio | 🔥🔥🔥 Muy Alto |
| **EP2-03** | Textos de Comprensión Lectora Extensa (3+ párrafos) | A1-B1 | 🔴 P0 | Medio-Alto | 🔥🔥🔥 Muy Alto |
| **EP4-01** | Buscador y Conjugador de Verbos (`verbs.json`) | Global | ✅ Hecha | Medio | 🔥🔥🔥 Muy Alto |
| **EP3-01** | Gimnasio de Declinaciones Interactivo | A1-B1 | ✅ Hecha | Medio | 🔥🔥🔥 Muy Alto |
| **EP2-02** | Expansión de Vocabulario & Flashcards con color | A1-B1 | 🟡 P1 | Medio | 🔥🔥 Alto |
| **EP5-01** | Roleplay Trainer (4 diálogos ramificados) | A1-B1 | 🟡 P1 | Alto | 🔥🔥 Alto |
| **EP6-01** | Entrenador de Fonética y Parejas Mínimas | A1-B1 | 🟢 P2 | Bajo | 🔥🔥 Alto |
| **EP6-02** | TE-KA-MO-LO y Falsos Amigos | A2-B1 | 🟢 P2 | Bajo | 🔥 Medio |
| **EP7-01** | Taller de Redacción B1 (Cartas e Emails) | B1 | 🟢 P2 | Medio | 🔥🔥 Alto |
| **EP8-01** | PWA & Offline Service Worker | Global | ⚪ P3 | Medio | 🔥 Medio |
| **EP8-02** | Creación del Nivel B2 Oficial | B2 | ⚪ P3 | Alto | 🔥🔥 Alto |

---
*Documento vivo mantenido por el equipo didáctico de DeutschMeister.*
