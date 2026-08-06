# Demostración Guiada de Agentes Especializados de Microsoft 365 Copilot

## 1. Metadatos

| Campo | Valor |
|-------|-------|
| **Duración** | 26 minutos |
| **Complejidad** | Media |
| **Nivel de Bloom** | Aplicar |
| **Modalidad** | Demostración guiada por el instructor con participación observacional de los estudiantes |

---

## 2. Descripción General

En esta práctica, el instructor ejecutará demostraciones en tiempo real de los cinco agentes especializados del catálogo de Microsoft 365 Copilot: **Analista**, **Investigador**, **Ideas**, **Prompt Coach** y **Writing Coach**. Los participantes observarán cómo cada agente aborda tareas específicas en contextos empresariales reales, tomarán notas sobre las diferencias funcionales respecto al Copilot base y relacionarán cada agente con áreas organizacionales concretas. Los artefactos generados servirán como referencia para la Práctica 2, donde se creará un agente personalizado.

---

## 3. Objetivos de Aprendizaje

Al completar esta práctica, los participantes serán capaces de:

- [ ] Identificar las diferencias funcionales entre Microsoft 365 Copilot base y los agentes especializados del catálogo, comprendiendo cuándo y por qué utilizar cada uno.
- [ ] Describir el funcionamiento de los agentes Analista, Investigador e Ideas aplicados a escenarios de Finanzas, Operaciones, Ingeniería, Proyectos, Dirección, Recursos Humanos y áreas Comerciales.
- [ ] Explicar cómo los agentes Prompt Coach y Writing Coach mejoran la calidad de los prompts y la redacción de contenido empresarial.
- [ ] Relacionar cada agente especializado con al menos dos casos de uso concretos en áreas organizacionales distintas.
- [ ] Diferenciar los tres pilares de un agente (instrucciones, conocimiento y acciones) observando su manifestación práctica en cada demostración.

---

## 4. Prerrequisitos

### Conocimientos Previos

| Requisito | Nivel |
|-----------|-------|
| Comprensión básica de qué es Microsoft 365 Copilot y su función como asistente de IA | Básico |
| Experiencia navegando Microsoft Teams (chat, canales, barra lateral) | Básico |
| Familiaridad con Microsoft 365 (Word, Excel, Outlook) | Básico |
| Comprensión del concepto de agente de IA según la Lección 1.1 (instrucciones, conocimiento, acciones) | Básico |

### Acceso Requerido

| Recurso | Detalle |
|---------|---------|
| Cuenta Microsoft 365 corporativa | Con licencia de Microsoft 365 Copilot activa y asignada |
| Microsoft Teams | Versión de escritorio 24.4.5.11 o acceso web |
| Copilot Chat | Acceso vía https://copilot.microsoft.com o Teams |
| Agentes del catálogo habilitados | Analista, Investigador, Ideas, Prompt Coach y Writing Coach visibles en el catálogo de agentes |
| Archivo de datos de demostración | Hoja de cálculo Excel con métricas financieras/operaciones (proporcionada por el instructor) |

---

## 5. Entorno del Laboratorio

### Hardware Mínimo (Participantes)

| Componente | Especificación |
|------------|---------------|
| Procesador | Intel Core i5 8ª gen. / AMD Ryzen 5 3000 o superior (64 bits) |
| RAM | 8 GB mínimo (16 GB recomendado) |
| Almacenamiento | 5 GB disponibles |
| Monitor | 1280×720 mínimo (1920×1080 recomendado) |
| Red | 10 Mbps mínimo (25 Mbps recomendado) |
| Audio | Micrófono y altavoces/auriculares funcionales |

### Software Requerido

| Aplicación | Versión |
|------------|---------|
| Microsoft Edge | 124.0.2478.97 o superior |
| Microsoft Teams | 24.4.5.11 (escritorio) |
| Microsoft 365 Copilot | Servicio en la nube (GA) |
| Microsoft Excel | Versión 2404 (Build 17531.20152) |
| Microsoft Word | Versión 2404 (Build 17531.20152) |

### Configuración Previa del Tenant (Responsabilidad del Administrador)

Antes de iniciar la sesión, el administrador del tenant debe verificar:

1. Navegar a **Microsoft 365 Admin Center** > **Settings** > **Copilot** > **Manage agents**.
2. Confirmar que los siguientes agentes del catálogo están habilitados:
   - Analyst (Analista)
   - Researcher (Investigador)
   - Ideas
   - Prompt Coach
   - Writing Coach
3. Verificar en **Copilot settings** > **Agent Builder** que la opción `Users can create agents` está habilitada (necesario para la Práctica 2).

---

## 6. Procedimiento Paso a Paso

### Paso 1: Acceso al Entorno de Copilot Chat y Exploración del Catálogo de Agentes

**Objetivo:** Acceder a Microsoft 365 Copilot Chat y localizar los agentes especializados del catálogo, estableciendo la diferencia visual y funcional entre el Copilot base y los agentes.

**Instrucciones:**

1. Abrir **Microsoft Teams** (versión de escritorio) o navegar a https://copilot.microsoft.com en Microsoft Edge.
2. Iniciar sesión con la cuenta corporativa que tiene licencia de Microsoft 365 Copilot asignada.
3. En Teams: hacer clic en el ícono de **Copilot** en la barra lateral izquierda. En la web: confirmar que se muestra la interfaz de Copilot Chat.
4. Identificar la interfaz principal de Copilot Chat. Observar que esta es la experiencia **base** — un asistente general que responde a cualquier tipo de consulta.
5. Localizar la sección de **Agentes** (Agents). En Teams: dentro del panel de Copilot Chat, buscar el botón o pestaña "Agentes" o "Agents". En la web: buscar el ícono de agentes en el panel lateral o en la barra superior.
6. Explorar el catálogo de agentes disponibles. Identificar visualmente los cinco agentes que se demostrarán:
   - **Analyst** (Analista) — ícono con gráfico/datos
   - **Researcher** (Investigador) — ícono con lupa/libro
   - **Ideas** — ícono con bombilla/creatividad
   - **Prompt Coach** — ícono con diálogo/mejora
   - **Writing Coach** — ícono con pluma/documento

7. El instructor explicará en este punto la diferencia conceptual:

   > **Copilot base:** Asistente generalista que responde a cualquier pregunta usando el LLM + datos de Microsoft Graph.
   >
   > **Agente especializado:** Entidad con instrucciones predefinidas, conocimiento enfocado y acciones específicas que lo hacen experto en un dominio particular.

**Resultado Esperado:** Los participantes visualizan el catálogo de agentes dentro de Copilot Chat y comprenden la distinción entre el asistente base y los agentes especializados.

**Verificación:** Los cinco agentes (Analyst, Researcher, Ideas, Prompt Coach, Writing Coach) aparecen listados en el catálogo de agentes del tenant.

---

### Paso 2: Demostración del Agente Analista — Escenario de Finanzas y Operaciones

**Objetivo:** Demostrar cómo el agente Analista procesa datos estructurados, identifica tendencias, genera resúmenes ejecutivos y produce visualizaciones a partir de hojas de cálculo, aplicado a contextos de Finanzas y Operaciones.

**Instrucciones:**

1. Desde el catálogo de agentes, seleccionar el agente **Analyst** (Analista). Esto abrirá una nueva conversación contextualizada con las capacidades del agente.

2. El instructor cargará un archivo de Excel previamente preparado con datos financieros de ejemplo. El archivo contiene:
   - Hoja 1: Ingresos trimestrales por línea de negocio (Q1–Q4, 3 líneas de negocio)
   - Hoja 2: Costos operativos mensuales por departamento
   - Hoja 3: KPIs de producción (unidades producidas, defectos, tiempo de ciclo)

3. Adjuntar el archivo de Excel a la conversación con el agente Analista (arrastrar y soltar o usar el ícono de adjuntar archivo).

4. Enviar el siguiente prompt al agente Analista — **Escenario Finanzas:**

```
Analiza los datos de ingresos trimestrales del archivo adjunto. Identifica qué línea de negocio 
tuvo el mayor crecimiento porcentual entre Q1 y Q4, cuál mostró declive, y genera un resumen 
ejecutivo de 3 párrafos con recomendaciones para el CFO.
```

5. Observar la respuesta del agente. El instructor destacará:
   - Cómo el agente accede a los datos del archivo (pilar: **conocimiento**)
   - Cómo estructura el análisis siguiendo un razonamiento lógico (ciclo **ReAct**)
   - Cómo genera un resumen ejecutivo con tono profesional (pilar: **instrucciones**)

6. Enviar un segundo prompt — **Escenario Operaciones:**

```
Usando la hoja de KPIs de producción, identifica los meses con mayor tasa de defectos 
y correlaciona con el tiempo de ciclo. ¿Hay algún patrón? Presenta los hallazgos en 
formato de tabla y sugiere 3 acciones correctivas para el Director de Operaciones.
```

7. Observar cómo el agente:
   - Realiza correlaciones entre variables
   - Presenta datos en formato tabular
   - Formula recomendaciones accionables

8. (Opcional) El instructor puede solicitar una visualización:

```
Genera un gráfico que muestre la relación entre tasa de defectos y tiempo de ciclo 
por mes.
```

**Resultado Esperado:**

- El agente Analista produce un resumen ejecutivo estructurado con identificación clara de tendencias financieras.
- Genera una tabla de correlación entre KPIs operativos con patrones identificados.
- Las recomendaciones son específicas y relevantes para el contexto empresarial.
- El tono es profesional y adecuado para presentar a nivel directivo.

**Verificación:**
- La respuesta del agente referencia datos específicos del archivo Excel (cifras, porcentajes, meses).
- El formato de salida es estructurado (párrafos numerados, tablas, viñetas).
- Las recomendaciones son accionables y no genéricas.

---

### Paso 3: Demostración del Agente Investigador — Escenario de Proyectos y Dirección

**Objetivo:** Demostrar cómo el agente Investigador sintetiza información de múltiples fuentes sobre temas complejos, generando reportes de investigación estructurados aplicables a la toma de decisiones estratégicas.

**Instrucciones:**

1. Cerrar o minimizar la conversación anterior. Regresar al catálogo de agentes y seleccionar el agente **Researcher** (Investigador).

2. Enviar el siguiente prompt — **Escenario Proyectos (Ingeniería):**

```
Investiga las mejores prácticas actuales para implementar metodologías ágiles en equipos 
de ingeniería de software distribuidos (remotos). Necesito comprender: (1) los frameworks 
más adoptados en 2024, (2) los desafíos principales reportados por la industria, 
(3) herramientas tecnológicas recomendadas, y (4) métricas de éxito. Presenta la 
información en un reporte estructurado con fuentes.
```

3. Observar la respuesta del agente. El instructor destacará:
   - La capacidad del agente para sintetizar información de múltiples fuentes web
   - La estructura del reporte (secciones, subsecciones, referencias)
   - El **grounding** (anclaje) en fuentes verificables
   - La profundidad del análisis comparado con una búsqueda manual

4. Enviar un segundo prompt — **Escenario Dirección / Recursos Humanos:**

```
Investiga las tendencias actuales en retención de talento tecnológico en Latinoamérica. 
Quiero entender: qué factores son más valorados por los profesionales de tecnología 
al elegir empleador, qué estrategias de retención están implementando las empresas 
líderes, y cuál es el impacto económico de la rotación de personal en equipos de TI. 
Genera un brief ejecutivo para presentar al Comité de Dirección.
```

5. Observar cómo el agente:
   - Contextualiza la investigación a la región especificada (Latinoamérica)
   - Diferencia entre datos cuantitativos y cualitativos
   - Genera un brief con formato ejecutivo (conciso, con datos clave resaltados)
   - Incluye referencias o indica las fuentes consultadas

6. El instructor comparará brevemente con lo que ocurriría al hacer la misma pregunta al Copilot base, destacando:
   - Mayor profundidad y estructura en la respuesta del agente Investigador
   - Mejor organización de la información por secciones
   - Inclusión de fuentes y datos más específicos

**Resultado Esperado:**

- El agente Investigador produce un reporte multi-sección con información actualizada y relevante.
- Las fuentes están citadas o referenciadas.
- El formato es apropiado para consumo ejecutivo.
- La información es específica al contexto solicitado (región, industria, período).

**Verificación:**
- El reporte contiene al menos 3-4 secciones claramente diferenciadas.
- Se mencionan fuentes, estudios o datos verificables.
- El tono y nivel de detalle son apropiados para un Comité de Dirección.

---

### Paso 4: Demostración del Agente Ideas — Escenario Comercial y Operaciones

**Objetivo:** Demostrar cómo el agente Ideas genera propuestas creativas y estructuradas para desafíos empresariales, facilitando sesiones de brainstorming individual o grupal en contextos Comerciales y de Operaciones.

**Instrucciones:**

1. Regresar al catálogo de agentes y seleccionar el agente **Ideas**.

2. Enviar el siguiente prompt — **Escenario Comercial:**

```
Somos una empresa B2B de servicios de consultoría tecnológica con 200 empleados. 
Nuestras ventas se han estancado en los últimos 2 trimestres. Necesito ideas innovadoras 
para: (1) generar nuevos canales de adquisición de clientes, (2) diferenciar nuestra 
propuesta de valor frente a competidores más grandes, y (3) crear una estrategia de 
contenido que posicione a nuestros consultores como líderes de opinión. 
Dame al menos 8 ideas concretas y accionables.
```

3. Observar la respuesta del agente. El instructor destacará:
   - La cantidad y variedad de ideas generadas
   - El nivel de detalle y accionabilidad de cada propuesta
   - La estructura organizada (numeración, categorización)
   - Cómo el agente va más allá de lo obvio, proponiendo enfoques creativos

4. Solicitar una profundización en una idea específica:

```
Profundiza en la idea número [X]. Dame un plan de implementación en 4 semanas, 
los recursos necesarios, los riesgos principales y cómo mediríamos el éxito.
```

5. Enviar un tercer prompt — **Escenario Operaciones:**

```
Nuestra planta de manufactura tiene un problema recurrente: el tiempo de cambio de línea 
(changeover) entre productos es de 45 minutos en promedio, lo cual reduce nuestra 
capacidad productiva un 15%. Genera ideas para reducir este tiempo a menos de 20 minutos, 
considerando que tenemos presupuesto limitado y no podemos detener la producción 
para una reingeniería completa.
```

6. Observar cómo el agente:
   - Adapta las ideas al contexto de restricciones mencionadas
   - Combina enfoques técnicos y organizacionales
   - Prioriza o categoriza las ideas por factibilidad
   - Demuestra conocimiento de metodologías industriales (SMED, Lean, etc.)

**Resultado Esperado:**

- El agente Ideas genera al menos 8 propuestas diversas y no genéricas para el escenario comercial.
- Las ideas son accionables (incluyen qué hacer, no solo qué pensar).
- En el escenario de Operaciones, las propuestas respetan las restricciones planteadas.
- La profundización incluye un plan estructurado con timeline, recursos y métricas.

**Verificación:**
- Las ideas no son repetitivas ni superficiales.
- Al menos 3 de las ideas propuestas son innovadoras (no las primeras que vendrían a la mente).
- La profundización contiene elementos concretos: fechas, roles, indicadores.

---

### Paso 5: Demostración del Agente Prompt Coach — Mejora de Prompts Empresariales

**Objetivo:** Demostrar cómo el agente Prompt Coach ayuda a reformular y mejorar prompts mal estructurados, enseñando al usuario técnicas para obtener mejores resultados de cualquier herramienta de IA.

**Instrucciones:**

1. Regresar al catálogo de agentes y seleccionar el agente **Prompt Coach**.

2. Presentar un prompt "mal formulado" y solicitar mejora — **Escenario Ingeniería:**

```
Tengo este prompt que uso con Copilot pero no me da buenos resultados: 
"Hazme un reporte de los servidores". 
¿Cómo puedo mejorarlo para obtener información útil sobre el estado de nuestra 
infraestructura de TI?
```

3. Observar la respuesta del agente. El instructor destacará:
   - Cómo el agente identifica las debilidades del prompt original (vago, sin contexto, sin formato deseado)
   - Las sugerencias específicas de mejora (añadir contexto, especificar formato, definir audiencia)
   - La versión mejorada del prompt que propone
   - Los principios de prompting que enseña (especificidad, contexto, formato, rol)

4. Enviar un segundo ejemplo — **Escenario Recursos Humanos:**

```
Quiero mejorar este prompt: "Escribe un correo para los empleados sobre el cambio 
de política". ¿Qué le falta y cómo lo reformularías para que Copilot genere un correo 
profesional y efectivo?
```

5. Observar cómo el agente:
   - Descompone el prompt original en sus elementos faltantes
   - Explica POR QUÉ cada elemento es importante
   - Ofrece una versión mejorada con todos los elementos incluidos
   - Opcionalmente, ofrece variantes según el tono deseado

6. El instructor realizará una comparación en vivo:
   - Copiar el prompt original y enviarlo al Copilot base → mostrar resultado genérico
   - Copiar el prompt mejorado por Prompt Coach y enviarlo al Copilot base → mostrar resultado significativamente mejor
   - Esto demuestra el valor tangible del agente Prompt Coach

**Resultado Esperado:**

- El agente Prompt Coach identifica claramente las deficiencias del prompt original.
- Proporciona una versión mejorada con contexto, especificidad, formato y audiencia definidos.
- Explica los principios detrás de la mejora (no solo corrige, sino que enseña).
- La comparación en vivo muestra una diferencia notable en la calidad de las respuestas.

**Verificación:**
- El prompt mejorado contiene al menos 3 elementos adicionales respecto al original (contexto, audiencia, formato, tono, alcance).
- La explicación incluye principios transferibles a otros prompts.
- La demostración comparativa muestra diferencia cualitativa evidente.

---

### Paso 6: Demostración del Agente Writing Coach — Refinamiento de Contenido Empresarial

**Objetivo:** Demostrar cómo el agente Writing Coach mejora la calidad de textos empresariales en términos de tono, claridad, estructura y persuasión, aplicado a documentos de distintas áreas organizacionales.

**Instrucciones:**

1. Regresar al catálogo de agentes y seleccionar el agente **Writing Coach**.

2. Presentar un texto empresarial que necesita mejora — **Escenario Dirección:**

```
Necesito mejorar este texto que enviaré como comunicado a toda la empresa:

"Hola a todos. Les quiero decir que a partir del próximo mes vamos a cambiar 
la forma en que hacemos las evaluaciones de desempeño. Ahora va a ser diferente 
porque vamos a usar una nueva herramienta y los criterios van a cambiar un poco. 
Si tienen dudas pregunten a su jefe. Gracias."

Quiero que suene profesional, claro, motivador y que genere confianza en el cambio. 
La audiencia son 500 empleados de todos los niveles.
```

3. Observar la respuesta del agente. El instructor destacará:
   - Cómo el agente identifica los problemas del texto original (tono informal, falta de estructura, vaguedad, falta de motivación)
   - La versión mejorada con tono ejecutivo apropiado
   - Las explicaciones de por qué cada cambio mejora la comunicación
   - Sugerencias de estructura (saludo, contexto, cambio, beneficios, próximos pasos, cierre)

4. Enviar un segundo ejemplo — **Escenario Comercial (propuesta de valor):**

```
Revisa y mejora este párrafo de nuestra propuesta comercial:

"Nuestra empresa tiene mucha experiencia y hacemos cosas de tecnología. Podemos 
ayudarle con sus problemas de TI porque tenemos gente que sabe mucho. Nuestros 
precios son buenos y trabajamos rápido."

Necesito que suene profesional, diferenciador y persuasivo para un Director de 
Tecnología que está evaluando 3 proveedores.
```

5. Observar cómo el agente:
   - Transforma lenguaje vago en proposiciones de valor específicas
   - Ajusta el tono para la audiencia objetivo (CTO/Director)
   - Incorpora elementos persuasivos (datos, diferenciadores, resultados)
   - Mantiene la esencia del mensaje original pero lo eleva profesionalmente

6. (Opcional) Solicitar variantes de tono:

```
Dame 3 versiones del mismo párrafo: una formal-corporativa, una conversacional-profesional, 
y una directa-ejecutiva. Explica cuándo usar cada una.
```

**Resultado Esperado:**

- El agente Writing Coach produce versiones significativamente mejoradas de ambos textos.
- Cada mejora viene acompañada de explicaciones sobre los principios de escritura aplicados.
- Las versiones son apropiadas para la audiencia y contexto especificados.
- El agente demuestra versatilidad al adaptar el mismo contenido a diferentes tonos.

**Verificación:**
- El texto mejorado es notablemente más profesional, claro y estructurado que el original.
- Las explicaciones mencionan principios de comunicación (claridad, concisión, estructura, tono, audiencia).
- Las variantes de tono son distinguibles entre sí y apropiadas para sus contextos.

---

### Paso 7: Síntesis Comparativa y Mapeo a Áreas Organizacionales

**Objetivo:** Consolidar las observaciones de todas las demostraciones, creando un mapa mental de cuándo usar cada agente según el área organizacional y el tipo de tarea.

**Instrucciones:**

1. El instructor presentará (en pantalla compartida) la siguiente tabla resumen, completándola con los participantes basándose en lo observado:

| Agente | Tipo de Tarea | Áreas Organizacionales | Cuándo Usarlo (vs. Copilot base) |
|--------|---------------|------------------------|----------------------------------|
| **Analista** | Análisis de datos, tendencias, correlaciones, resúmenes ejecutivos | Finanzas, Operaciones, Ingeniería | Cuando tienes datos estructurados y necesitas insights profundos |
| **Investigador** | Síntesis de información compleja, reportes de investigación | Proyectos, Dirección, RRHH, Estrategia | Cuando necesitas investigar un tema a profundidad con múltiples fuentes |
| **Ideas** | Brainstorming, generación de propuestas, creatividad estructurada | Comercial, Operaciones, Marketing, Innovación | Cuando enfrentas un desafío y necesitas opciones diversas y creativas |
| **Prompt Coach** | Mejora de prompts, enseñanza de técnicas de prompting | Todas las áreas | Cuando tus prompts no generan resultados satisfactorios |
| **Writing Coach** | Refinamiento de textos, ajuste de tono, mejora de claridad | Dirección, RRHH, Comercial, Comunicaciones | Cuando necesitas elevar la calidad de un texto empresarial |

2. El instructor formulará las siguientes preguntas de reflexión a los participantes:

   - ¿En qué se diferencia la respuesta del agente Analista de lo que obtendríamos con el Copilot base al analizar el mismo archivo?
   - ¿Qué elementos del ciclo ReAct (Razonar → Actuar → Observar) pudieron identificar en las demostraciones?
   - ¿Cómo se manifiestan los tres pilares (instrucciones, conocimiento, acciones) en cada agente observado?

3. El instructor destacará el vínculo con la Práctica 2:

   > "En la siguiente práctica, ustedes crearán su propio agente personalizado usando Agent Builder. Podrán combinar capacidades similares a las que acabamos de ver — definirán instrucciones específicas, conectarán fuentes de conocimiento y configurarán acciones — para resolver un problema de su propia área organizacional."

4. Los participantes registran en sus notas:
   - Al menos un caso de uso por agente aplicable a su propia área de trabajo
   - Un prompt de ejemplo que les gustaría probar con cada agente
   - Ideas para el agente personalizado que crearán en la Práctica 2

**Resultado Esperado:**

- Los participantes tienen una comprensión clara y diferenciada de los cinco agentes.
- Pueden articular cuándo usar cada agente versus el Copilot base.
- Han identificado aplicaciones concretas para su contexto laboral.

**Verificación:**
- Los participantes pueden responder verbalmente a las preguntas de reflexión.
- Cada participante ha identificado al menos un caso de uso personal por agente.

---

## 7. Validación y Pruebas

### Criterios de Éxito de la Práctica

| Criterio | Indicador de Logro |
|----------|-------------------|
| Acceso al catálogo de agentes | Los 5 agentes son visibles y accesibles en el tenant |
| Demostración del Analista | El agente procesó datos del Excel y generó análisis con cifras específicas |
| Demostración del Investigador | El agente produjo un reporte estructurado con fuentes identificables |
| Demostración de Ideas | El agente generó al menos 8 propuestas diversas y accionables |
| Demostración de Prompt Coach | El agente mejoró un prompt y explicó los principios aplicados |
| Demostración de Writing Coach | El agente produjo una versión significativamente mejorada del texto original |
| Comprensión de los participantes | Los participantes pueden diferenciar verbalmente los 5 agentes |

### Preguntas de Verificación para los Participantes

Tras la demostración, el instructor puede formular estas preguntas para verificar comprensión:

1. **¿Cuál es la diferencia principal entre pedirle al Copilot base que "analice un archivo de Excel" versus usar el agente Analista?**
   - *Respuesta esperada:* El agente Analista tiene instrucciones especializadas para análisis de datos, genera visualizaciones, identifica patrones automáticamente y estructura la salida en formato ejecutivo. El Copilot base daría una respuesta más genérica y menos profunda.

2. **Si necesito generar 10 ideas para un nuevo producto, ¿qué agente usaría y por qué no simplemente el Copilot base?**
   - *Respuesta esperada:* El agente Ideas, porque está optimizado para brainstorming — genera más cantidad, mayor diversidad y propuestas más accionables que el Copilot base.

3. **¿Cómo se relacionan los tres pilares de un agente (instrucciones, conocimiento, acciones) con lo que observamos en el agente Investigador?**
   - *Respuesta esperada:* Instrucciones = comportamiento de investigador (buscar, sintetizar, citar fuentes); Conocimiento = acceso a fuentes web y datos organizacionales; Acciones = capacidad de buscar en múltiples fuentes y estructurar reportes.

---

## 8. Solución de Problemas

### Problema 1: Los agentes del catálogo no aparecen en Copilot Chat

**Síntomas:**
- Al navegar a la sección de Agentes en Copilot Chat (Teams o web), no se muestran los agentes Analyst, Researcher, Ideas, Prompt Coach o Writing Coach.
- Aparece un catálogo vacío o con mensaje "No hay agentes disponibles".

**Causa:**
Los agentes del catálogo no han sido habilitados por el administrador del tenant, o la habilitación se realizó hace menos de 24 horas y la propagación no ha completado.

**Solución:**
1. El administrador del tenant debe navegar a: **Microsoft 365 Admin Center** > **Settings** > **Copilot** > **Manage agents** > **Catalog agents**.
2. Verificar que cada agente (Analyst, Researcher, Ideas, Prompt Coach, Writing Coach) tiene el estado **Enabled** (Habilitado).
3. Si alguno está deshabilitado, habilitarlo y esperar hasta 24 horas para la propagación completa.
4. Como solución temporal inmediata: el instructor puede intentar acceder directamente a cada agente mediante su URL directa en Copilot Chat o reiniciando la sesión de Teams (cerrar completamente y volver a abrir).
5. Verificar que el usuario tiene una licencia de **Microsoft 365 Copilot** activa (no solo Microsoft 365 estándar).

---

### Problema 2: El agente Analista no puede leer o procesar el archivo de Excel adjunto

**Síntomas:**
- Al adjuntar el archivo Excel y enviar el prompt, el agente responde con un mensaje genérico sin datos específicos.
- El agente indica que "no puede acceder al archivo" o genera un análisis que no corresponde a los datos del archivo.
- El archivo aparece adjunto pero el agente no lo referencia en su respuesta.

**Causa:**
El archivo puede exceder el límite de tamaño para procesamiento en chat (generalmente 10 MB), estar en un formato no compatible (.xls antiguo en lugar de .xlsx), tener protección con contraseña, o estar almacenado en una ubicación a la que el agente no tiene permisos de acceso.

**Solución:**
1. Verificar que el archivo está en formato **.xlsx** (no .xls, .csv ni .xlsm con macros).
2. Confirmar que el tamaño del archivo no excede **10 MB**.
3. Asegurar que el archivo **no está protegido con contraseña** ni tiene hojas protegidas.
4. Si el archivo está en SharePoint, verificar que el usuario tiene permisos de lectura sobre el archivo.
5. Como alternativa: subir el archivo directamente a OneDrive del usuario y luego referenciarlo en el prompt con su nombre: `"Analiza el archivo 'Datos_Financieros_Q4.xlsx' que está en mi OneDrive"`.
6. Si persiste el problema: copiar los datos relevantes directamente en el prompt como texto o tabla (para datasets pequeños) para verificar que el agente funciona correctamente con los datos.

---

## 9. Limpieza

Al finalizar esta práctica demostrativa:

1. **Conversaciones de demostración:** No es necesario eliminarlas. Los participantes pueden revisarlas posteriormente como referencia para la Práctica 2.

2. **Archivos de demostración:** El instructor puede compartir el archivo Excel de ejemplo con los participantes (vía chat de Teams o carpeta compartida) para que puedan replicar la demostración del agente Analista por su cuenta.

3. **Notas de los participantes:** Recordar a los participantes que conserven sus notas (casos de uso identificados, prompts de ejemplo, ideas para agente personalizado) ya que serán insumo directo para la Práctica 2.

4. **Sesiones de agentes:** Las conversaciones con agentes del catálogo se mantienen en el historial de Copilot Chat y no consumen almacenamiento significativo. No requieren limpieza.

---

## 10. Resumen

### Conceptos Clave Cubiertos

En esta práctica demostrativa se exploraron los cinco agentes especializados del catálogo de Microsoft 365 Copilot:

| Agente | Capacidad Principal Demostrada |
|--------|-------------------------------|
| **Analista** | Procesamiento de datos estructurados, identificación de tendencias, generación de resúmenes ejecutivos |
| **Investigador** | Síntesis de información compleja de múltiples fuentes con estructura de reporte |
| **Ideas** | Generación de propuestas creativas, diversas y accionables para desafíos empresariales |
| **Prompt Coach** | Diagnóstico y mejora de prompts con enseñanza de principios transferibles |
| **Writing Coach** | Refinamiento de textos empresariales en tono, claridad, estructura y persuasión |

### Conexión con la Lección 1.1

Las demostraciones ilustraron en la práctica los conceptos teóricos de la Lección 1.1:
- **Tres pilares del agente** (instrucciones, conocimiento, acciones): cada agente demostró comportamiento especializado gracias a sus instrucciones predefinidas, acceso a fuentes de datos relevantes y capacidad de ejecutar acciones específicas.
- **Ciclo ReAct**: los agentes razonaron sobre las tareas, ejecutaron acciones (búsqueda, análisis, generación) y produjeron resultados iterativamente.
- **Grounding**: las respuestas estuvieron ancladas en datos reales (archivo Excel, fuentes web) y no en suposiciones.
- **Complemento al trabajo humano**: en todos los escenarios, el agente amplificó la capacidad del usuario sin reemplazar su juicio final.

### Preparación para la Práctica 2

Los participantes ahora tienen:
- ✅ Comprensión clara de qué puede hacer un agente especializado
- ✅ Ejemplos concretos de prompts efectivos para agentes
- ✅ Ideas sobre qué tipo de agente personalizado podrían crear
- ✅ Conocimiento de los tres pilares que deberán configurar en Agent Builder

### Recursos Adicionales

| Recurso | URL |
|---------|-----|
| Documentación oficial: Agentes de Microsoft 365 Copilot | https://learn.microsoft.com/es-es/microsoft-365-copilot/extensibility/agents-overview |
| Guía de uso de Copilot Chat | https://support.microsoft.com/es-es/copilot |
| Microsoft Copilot Studio (Agent Builder) | https://copilotstudio.microsoft.com |
| Blog de Microsoft 365: Nuevos agentes | https://www.microsoft.com/en-us/microsoft-365/blog/2024/11/19/introducing-new-agents-in-microsoft-365/ |
| Guía de adopción de Copilot | https://adoption.microsoft.com/es-es/copilot/ |

---
