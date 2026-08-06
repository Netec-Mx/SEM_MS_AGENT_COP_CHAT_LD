# Creación de un Agente Personalizado con Agent Builder — Enfoque Automático y Manual

## Metadata

| Campo | Valor |
|-------|-------|
| **Duración** | 30 minutos |
| **Complejidad** | Alta |
| **Nivel Bloom** | Crear (Create) |
| **Rol** | Instructor (demostración guiada con participación de los asistentes) |
| **Entregable** | Dos agentes personalizados funcionales: uno generado por lenguaje natural y otro configurado manualmente |

---

## Visión General

En esta práctica el instructor creará un agente personalizado utilizando Agent Builder integrado en Microsoft 365 Copilot, demostrando dos enfoques complementarios. Primero, se utilizará la generación automática mediante una descripción en lenguaje natural para obtener una configuración inicial rápida. Después, se empleará la configuración manual para personalizar cada componente del agente con precisión. La práctica culmina con la adaptación del agente a un segundo caso de uso organizacional, demostrando la versatilidad de la herramienta para distintas áreas de negocio.

---

## Objetivos de Aprendizaje

Al completar esta práctica, serás capaz de:

- [ ] Crear un agente personalizado mediante generación automática a partir de una descripción en lenguaje natural, evaluando críticamente la configuración generada por Agent Builder.
- [ ] Configurar manualmente cada componente de un agente declarativo: nombre, descripción, instrucciones del sistema, iniciadores de conversación, tono y fuentes de conocimiento.
- [ ] Identificar y explicar el propósito funcional de cada componente de un agente y su impacto en el comportamiento del mismo.
- [ ] Aplicar buenas prácticas de ingeniería de prompts al diseño de instrucciones de sistema (system prompts) específicas y reutilizables.
- [ ] Proponer y justificar al menos un caso de uso de agente personalizado para un área organizacional específica, basándose en los escenarios observados en la Práctica 1.

---

## Prerrequisitos

### Conocimientos Previos

| Requisito | Descripción |
|-----------|-------------|
| Práctica 1 completada | Familiaridad con los agentes especializados (Analista, Investigador, Ideas, Prompt Coach, Writing Coach) |
| Concepto de prompt | Comprensión básica de cómo formular instrucciones para sistemas de IA generativa |
| Navegación en Microsoft 365 | Experiencia básica con Teams y la interfaz web de Microsoft 365 |
| Caso de uso identificado | Al menos un escenario organizacional candidato para un agente personalizado |

### Acceso y Permisos

| Requisito | Verificación |
|-----------|-------------|
| Licencia Microsoft 365 Copilot | Asignada y activa en la cuenta corporativa del instructor |
| Agent Builder habilitado | Admin Center > Copilot settings > "Users can create agents" = **Habilitado** |
| Acceso a Copilot Chat | Verificar inicio de sesión exitoso en https://microsoft365.com/copilot |
| Microsoft Teams actualizado | Versión 24.4.5.11 o superior con ícono de Copilot visible |
| Sitio de SharePoint (opcional) | Un sitio con documentos de ejemplo para conectar como fuente de conocimiento |

---

## Entorno del Laboratorio

### Hardware Mínimo

| Componente | Especificación |
|------------|---------------|
| Procesador | Intel Core i5 8ª gen. / AMD Ryzen 5 3000 o superior (64 bits) |
| RAM | 8 GB mínimo (16 GB recomendado) |
| Almacenamiento | 5 GB disponibles |
| Monitor | 1920×1080 recomendado (mínimo 1280×720) |
| Red | 10 Mbps mínimo (25 Mbps recomendado) |

### Software Requerido

| Software | Versión | Propósito |
|----------|---------|-----------|
| Microsoft Edge | 124.0.2478.97+ | Navegador principal para acceso web |
| Microsoft Teams | 24.4.5.11 (escritorio) | Plataforma de acceso alternativo y publicación |
| Microsoft 365 Copilot | Servicio en la nube (GA) | Motor de IA subyacente |
| Agent Builder | Servicio en la nube (integrado) | Herramienta de creación de agentes |

### Configuración Inicial

Antes de iniciar la práctica, el instructor debe verificar el acceso:

```
# Verificación 1: Acceso a Copilot Chat web
URL: https://microsoft365.com/copilot
Resultado esperado: Interfaz de Copilot Chat cargada con la cuenta corporativa

# Verificación 2: Visibilidad de Agent Builder
Navegación: Copilot Chat > Panel lateral > Ícono de agentes > "Crear un agente"
Resultado esperado: Se abre la interfaz de Agent Builder con dos paneles

# Verificación 3: Acceso alternativo vía Teams
Navegación: Teams > Copilot (barra lateral) > Agentes > "Crear un agente"
Resultado esperado: Misma interfaz de Agent Builder accesible desde Teams
```

---

## Instrucciones Paso a Paso

---

### BLOQUE A: Creación Mediante Lenguaje Natural (12 minutos)

---

### Paso 1: Acceder a Agent Builder desde Microsoft 365 Copilot Chat

**Objetivo:** Abrir la interfaz de Agent Builder y familiarizarse con los puntos de entrada disponibles.

**Instrucciones:**

1. Abrir Microsoft Edge y navegar a:
   ```
   https://microsoft365.com/copilot
   ```

2. Iniciar sesión con la cuenta corporativa que tiene licencia de Microsoft 365 Copilot asignada.

3. Una vez en la interfaz de Copilot Chat, localizar el panel lateral derecho donde aparecen los agentes disponibles.

4. Hacer clic en el botón **"Crear un agente"** (o **"Create an agent"** si la interfaz está en inglés). Este botón suele aparecer como un ícono "+" o como una opción destacada en la sección de agentes.

5. Verificar que se abre la interfaz de Agent Builder con dos paneles:
   - **Panel izquierdo:** Área de configuración (donde se define el agente).
   - **Panel derecho:** Área de vista previa (chat de prueba en tiempo real).

**Resultado Esperado:**

La interfaz de Agent Builder se muestra con un campo de texto prominente donde se puede escribir una descripción en lenguaje natural del agente deseado. El panel de vista previa está vacío o muestra un mensaje indicando que aún no se ha configurado el agente.

**Verificación:**

- [ ] La interfaz de Agent Builder está completamente cargada.
- [ ] Se visualizan claramente los dos paneles (configuración y vista previa).
- [ ] El campo para descripción en lenguaje natural es visible y editable.

---

### Paso 2: Redactar la Descripción en Lenguaje Natural del Agente

**Objetivo:** Generar automáticamente la configuración de un agente para el área de Recursos Humanos utilizando una descripción detallada en lenguaje natural.

**Instrucciones:**

1. En el campo de descripción de Agent Builder, escribir la siguiente descripción (o dictarla si se prefiere demostrar la accesibilidad de la herramienta):

   ```
   Quiero un agente que ayude al equipo de Recursos Humanos a realizar las 
   siguientes tareas:
   
   1. Redactar descripciones de puestos de trabajo claras y atractivas, 
      incluyendo responsabilidades, requisitos y competencias deseadas.
   2. Preparar preguntas de entrevista estructuradas basadas en competencias 
      para diferentes niveles de seniority (junior, semi-senior, senior).
   3. Resumir perfiles de candidatos destacando fortalezas, áreas de 
      desarrollo y nivel de ajuste al puesto.
   4. Generar plantillas de comunicación para procesos de onboarding.
   
   El tono debe ser profesional, inclusivo y alineado con una cultura 
   organizacional que valora la diversidad, la colaboración y el desarrollo 
   profesional continuo. El agente debe evitar sesgos de género, edad o 
   nacionalidad en todas sus respuestas.
   ```

2. Presionar **Enter** o hacer clic en el botón de generación (generalmente un ícono de envío o un botón "Crear").

3. **Esperar** mientras Agent Builder procesa la descripción. Esto puede tomar entre 5 y 15 segundos.

4. Observar cómo Agent Builder genera automáticamente los siguientes componentes:
   - **Nombre del agente** (ej.: "Asistente de Recursos Humanos")
   - **Descripción** (resumen del propósito del agente)
   - **Instrucciones del sistema** (system prompt detallado)
   - **Iniciadores de conversación** (sugerencias de preguntas para el usuario)

**Resultado Esperado:**

Agent Builder genera una configuración completa con un nombre descriptivo, instrucciones del sistema que reflejan las cuatro tareas especificadas, y al menos 3-4 iniciadores de conversación relevantes como:
- "Redacta una descripción de puesto para un Analista de Datos Senior"
- "Prepara 5 preguntas de entrevista por competencias para un rol de liderazgo"
- "Resume el siguiente perfil de candidato destacando su ajuste al puesto"

**Verificación:**

- [ ] Se generó un nombre coherente para el agente.
- [ ] Las instrucciones del sistema incluyen las cuatro tareas especificadas.
- [ ] Los iniciadores de conversación son relevantes y accionables.
- [ ] El tono profesional e inclusivo está reflejado en las instrucciones generadas.

---

### Paso 3: Analizar y Comentar la Configuración Generada

**Objetivo:** Evaluar críticamente cada componente generado automáticamente, identificando aciertos y áreas de mejora.

**Instrucciones:**

1. **Revisar el Nombre generado:**
   - ¿Es descriptivo y fácil de encontrar en un catálogo de agentes?
   - ¿Indica claramente a qué área o función pertenece?
   - Ejemplo de análisis: Si generó "Asistente HR" → considerar si "Asistente de Talento y Selección" sería más específico.

2. **Revisar la Descripción generada:**
   - ¿Resume adecuadamente las capacidades del agente en 1-2 oraciones?
   - ¿Un usuario que no conoce el agente entendería su propósito al leer la descripción?

3. **Revisar las Instrucciones del Sistema (System Prompt):**
   - Hacer clic en el campo de instrucciones para expandirlo y leer el texto completo.
   - Identificar los siguientes elementos en el prompt generado:

   | Elemento | Qué buscar | Presente (Sí/No) |
   |----------|-----------|-------------------|
   | Definición de rol | "Eres un asistente especializado en..." | |
   | Tareas específicas | Las 4 tareas que describimos | |
   | Restricciones de tono | Profesional, inclusivo, sin sesgos | |
   | Limitaciones de alcance | Qué NO debe hacer el agente | |
   | Formato de respuesta | Estructura sugerida para las respuestas | |

4. **Revisar los Iniciadores de Conversación:**
   - ¿Son variados (cubren diferentes tareas del agente)?
   - ¿Están redactados como lo haría un usuario real?
   - ¿Invitan a la acción inmediata?

5. Documentar mentalmente (o en notas) qué elementos necesitarían ajuste manual. Estos ajustes se realizarán en el Bloque B.

**Resultado Esperado:**

El instructor identifica al menos 2-3 áreas de mejora en la configuración generada automáticamente. Ejemplos típicos:
- Las instrucciones del sistema son demasiado genéricas y no incluyen ejemplos concretos.
- Falta una definición explícita de lo que el agente NO debe hacer (limitaciones).
- Los iniciadores podrían ser más específicos al contexto organizacional.

**Verificación:**

- [ ] Se revisaron los cuatro componentes principales (nombre, descripción, instrucciones, iniciadores).
- [ ] Se identificaron al menos 2 áreas de mejora concretas.
- [ ] Se comprende la diferencia entre lo que genera automáticamente Agent Builder y lo que requiere ajuste humano.

---

### Paso 4: Probar el Agente Generado en el Panel de Vista Previa

**Objetivo:** Validar el comportamiento inicial del agente antes de realizar ajustes manuales.

**Instrucciones:**

1. En el **panel derecho** (vista previa), escribir una consulta de prueba:

   ```
   Redacta una descripción de puesto para un Ingeniero de Software Senior 
   especializado en desarrollo backend con Python y arquitecturas en la nube.
   ```

2. Observar la respuesta generada por el agente. Evaluar:
   - ¿El tono es profesional e inclusivo como se solicitó?
   - ¿La estructura incluye secciones claras (responsabilidades, requisitos, competencias)?
   - ¿Evita sesgos de género en el lenguaje?

3. Realizar una segunda prueba con un iniciador de conversación diferente:

   ```
   Prepara 5 preguntas de entrevista por competencias para un candidato 
   a Gerente de Proyectos con 8 años de experiencia.
   ```

4. Evaluar si las preguntas generadas:
   - Son abiertas y basadas en comportamientos (formato STAR).
   - Varían en las competencias evaluadas.
   - Son apropiadas para el nivel de seniority indicado.

5. Realizar una prueba de límites (verificar restricciones):

   ```
   ¿Cuál es el salario promedio para este puesto en México?
   ```

6. Observar si el agente responde con información salarial (lo cual podría ser indeseable sin fuentes verificadas) o si indica que esa consulta está fuera de su alcance.

**Resultado Esperado:**

- La primera consulta genera una descripción de puesto estructurada con tono profesional.
- La segunda consulta produce preguntas de entrevista relevantes y bien formuladas.
- La tercera consulta (prueba de límites) probablemente genera una respuesta que idealmente debería ser restringida, evidenciando la necesidad de agregar limitaciones explícitas en las instrucciones del sistema.

**Verificación:**

- [ ] El agente responde coherentemente a las dos primeras consultas.
- [ ] Se identificó al menos un comportamiento que requiere ajuste (ej.: responde fuera de alcance).
- [ ] El panel de vista previa funciona correctamente para pruebas en tiempo real.

---

### BLOQUE B: Configuración Manual y Personalización (18 minutos)

---

### Paso 5: Acceder a la Vista de Edición Manual

**Objetivo:** Transicionar del modo de generación automática al modo de configuración manual para personalizar cada componente del agente.

**Instrucciones:**

1. Desde la interfaz de Agent Builder donde se encuentra el agente generado en el Bloque A, localizar la opción **"Configurar"** o **"Configure"** (generalmente una pestaña o botón en la parte superior del panel de configuración).

2. Al hacer clic, se despliegan todos los campos editables del agente en formato de formulario:
   - Nombre
   - Descripción
   - Instrucciones (Instructions / System Prompt)
   - Iniciadores de conversación (Conversation starters)
   - Fuentes de conocimiento (Knowledge sources)
   - Acciones (Actions)

3. Verificar que todos los campos son editables y contienen la información generada automáticamente en el Bloque A.

4. **Alternativa para crear desde cero:** Si se desea demostrar la creación completamente manual, hacer clic en "Nuevo agente" o volver al inicio de Agent Builder y seleccionar la opción de configuración manual (sin descripción en lenguaje natural). Esto presenta los mismos campos pero vacíos.

**Resultado Esperado:**

Se visualiza la interfaz completa de edición manual con todos los campos del agente accesibles. El instructor puede navegar entre los diferentes componentes y editarlos individualmente.

**Verificación:**

- [ ] Todos los campos de configuración son visibles y editables.
- [ ] Se puede alternar entre la vista de configuración y la vista previa sin perder cambios.

---

### Paso 6: Personalizar el Nombre y la Descripción del Agente

**Objetivo:** Definir una identidad clara y profesional para el agente que facilite su descubrimiento y comprensión por parte de los usuarios finales.

**Instrucciones:**

1. **Modificar el Nombre del agente.** Reemplazar el nombre generado por uno más específico y descriptivo:

   ```
   Nombre anterior (ejemplo): Asistente de Recursos Humanos
   Nombre nuevo: Copiloto de Talento y Selección
   ```

   **Buenas prácticas para el nombre:**
   - Máximo 3-5 palabras.
   - Indicar el área funcional o el propósito principal.
   - Evitar nombres genéricos como "Asistente" o "Helper".
   - Considerar que aparecerá en un catálogo junto a otros agentes.

2. **Modificar la Descripción del agente.** Escribir una descripción concisa (1-2 oraciones) que responda: ¿Qué hace? ¿Para quién? ¿Cuándo usarlo?

   ```
   Descripción nueva:
   Asiste al equipo de Talento y Selección en la redacción de descripciones 
   de puesto, preparación de entrevistas por competencias y análisis de 
   perfiles de candidatos. Ideal para reclutadores y hiring managers que 
   necesitan contenido profesional, inclusivo y alineado con la cultura 
   organizacional.
   ```

3. **(Opcional) Seleccionar o personalizar el ícono del agente** si la interfaz lo permite. Elegir un ícono que represente visualmente la función de RR. HH. (persona, maletín, etc.).

**Resultado Esperado:**

El agente tiene un nombre distintivo y una descripción que permite a cualquier usuario del tenant comprender inmediatamente su propósito sin necesidad de probarlo.

**Verificación:**

- [ ] El nombre es específico, conciso y diferenciable de otros agentes del catálogo.
- [ ] La descripción responde claramente qué hace, para quién y cuándo usarlo.

---

### Paso 7: Diseñar las Instrucciones del Sistema (System Prompt) — Componente Crítico

**Objetivo:** Redactar un system prompt detallado, estructurado y efectivo que defina con precisión el comportamiento, alcance y restricciones del agente.

**Instrucciones:**

1. Borrar las instrucciones generadas automáticamente y reemplazarlas con el siguiente system prompt diseñado manualmente. **Este es el componente más importante del agente:**

   ```
   ## ROL Y PROPÓSITO
   Eres "Copiloto de Talento y Selección", un asistente especializado en 
   procesos de atracción, selección e incorporación de talento. Tu audiencia 
   principal son reclutadores, especialistas de RR. HH. y hiring managers.

   ## TAREAS QUE PUEDES REALIZAR
   1. **Redacción de descripciones de puesto:** Genera descripciones 
      estructuradas con las secciones: Propósito del rol, Responsabilidades 
      principales (5-8 bullets), Requisitos indispensables, Requisitos 
      deseables, Competencias clave y Oferta de valor al candidato.
   2. **Preparación de entrevistas:** Crea preguntas de entrevista basadas 
      en competencias usando el formato STAR (Situación, Tarea, Acción, 
      Resultado). Adapta la complejidad al nivel de seniority indicado.
   3. **Análisis de perfiles:** Resume CVs o perfiles de candidatos 
      destacando: fortalezas principales, áreas de desarrollo, nivel de 
      ajuste al puesto (alto/medio/bajo) y recomendación fundamentada.
   4. **Comunicaciones de onboarding:** Genera plantillas de correo para 
      bienvenida, agenda de primera semana y presentación al equipo.

   ## TONO Y ESTILO
   - Profesional pero cercano.
   - Inclusivo: usa lenguaje neutro en género. Evita "el candidato" → 
     usa "la persona candidata" o alternar.
   - Específico: evita generalidades. Incluye ejemplos concretos cuando 
     sea posible.
   - Estructurado: usa encabezados, bullets y numeración para facilitar 
     la lectura.

   ## RESTRICCIONES Y LIMITACIONES
   - NO proporciones información salarial ni rangos de compensación.
   - NO realices evaluaciones psicológicas ni diagnósticos de personalidad.
   - NO generes contenido que discrimine por género, edad, nacionalidad, 
     orientación sexual, discapacidad o cualquier otra condición protegida.
   - NO respondas preguntas que no estén relacionadas con talento, 
     selección u onboarding. Si recibes una consulta fuera de alcance, 
     responde: "Esta consulta está fuera de mi especialidad. Te sugiero 
     consultar con [área correspondiente]."
   - Si no tienes información suficiente para responder, solicita 
     contexto adicional antes de generar contenido.

   ## FORMATO DE RESPUESTA
   - Inicia siempre con un encabezado que indique qué estás generando.
   - Usa formato Markdown para estructurar las respuestas.
   - Al final de cada respuesta, incluye una sección "💡 Sugerencias" 
     con 1-2 recomendaciones para mejorar o complementar el contenido.

   ## EJEMPLO DE INTERACCIÓN
   Usuario: "Necesito una descripción de puesto para Analista de Datos Junior"
   Respuesta esperada: Descripción completa con todas las secciones 
   mencionadas, lenguaje inclusivo, requisitos realistas para nivel junior 
   (1-2 años de experiencia), y sugerencias al final sobre cómo hacer 
   el puesto más atractivo para talento diverso.
   ```

2. **Explicar cada sección del system prompt mientras se escribe:**

   | Sección | Propósito | Impacto en el comportamiento |
   |---------|-----------|------------------------------|
   | Rol y propósito | Define la identidad del agente | Establece el marco de referencia para todas las respuestas |
   | Tareas | Enumera capacidades específicas | Limita y enfoca las respuestas a lo relevante |
   | Tono y estilo | Define la personalidad comunicativa | Garantiza consistencia en todas las interacciones |
   | Restricciones | Define lo que NO debe hacer | Previene respuestas inapropiadas o fuera de alcance |
   | Formato | Estructura las respuestas | Mejora la usabilidad y legibilidad |
   | Ejemplo | Muestra el comportamiento deseado | Calibra la calidad esperada de las respuestas |

3. Guardar las instrucciones (generalmente se guardan automáticamente o mediante un botón "Guardar").

**Resultado Esperado:**

Las instrucciones del sistema están completas, estructuradas con secciones claras y cubren los seis elementos fundamentales de un system prompt efectivo: rol, tareas, tono, restricciones, formato y ejemplo.

**Verificación:**

- [ ] El system prompt incluye las 6 secciones recomendadas.
- [ ] Las restricciones son explícitas y previenen comportamientos no deseados.
- [ ] Se incluye al menos un ejemplo de interacción esperada.
- [ ] El lenguaje es claro y no ambiguo.

---

### Paso 8: Configurar los Iniciadores de Conversación

**Objetivo:** Diseñar sugerencias de conversación que guíen a los usuarios hacia las capacidades principales del agente y reduzcan la barrera de entrada.

**Instrucciones:**

1. Localizar la sección **"Iniciadores de conversación"** (Conversation Starters) en el panel de configuración.

2. Eliminar los iniciadores generados automáticamente y reemplazarlos con los siguientes (configurar entre 4 y 6):

   ```
   Iniciador 1:
   "Redacta una descripción de puesto para [nombre del rol] de nivel [junior/senior]"
   
   Iniciador 2:
   "Prepara 6 preguntas de entrevista por competencias para evaluar [competencia] en candidatos a [puesto]"
   
   Iniciador 3:
   "Analiza el siguiente perfil de candidato y evalúa su ajuste para el puesto de [puesto]: [pegar perfil]"
   
   Iniciador 4:
   "Genera un correo de bienvenida para un nuevo colaborador que se incorpora al equipo de [área] el próximo [fecha]"
   
   Iniciador 5:
   "¿Qué competencias debería evaluar en una entrevista para un puesto de [rol] en el sector [industria]?"
   ```

3. **Buenas prácticas para iniciadores de conversación:**
   - Incluir placeholders entre corchetes `[...]` para indicar qué debe personalizar el usuario.
   - Cubrir las diferentes tareas del agente (no repetir la misma función).
   - Redactarlos como lo haría un usuario real, no como documentación técnica.
   - Mantenerlos concisos (máximo 1-2 líneas).

**Resultado Esperado:**

Los iniciadores de conversación aparecen como botones o sugerencias clicables en el panel de chat del agente, invitando al usuario a interactuar inmediatamente con tareas concretas.

**Verificación:**

- [ ] Se configuraron entre 4 y 6 iniciadores de conversación.
- [ ] Cada iniciador corresponde a una tarea diferente del agente.
- [ ] Los iniciadores usan placeholders que guían al usuario.

---

### Paso 9: Agregar Fuentes de Conocimiento (Knowledge Sources)

**Objetivo:** Conectar el agente con documentos organizacionales específicos que enriquezcan sus respuestas con información interna verificada.

**Instrucciones:**

1. Localizar la sección **"Conocimiento"** o **"Knowledge"** en el panel de configuración.

2. Hacer clic en **"Agregar fuente"** o **"Add knowledge source"**.

3. Seleccionar el tipo de fuente disponible. Las opciones típicas incluyen:

   | Tipo de fuente | Cuándo usarla | Ejemplo |
   |----------------|---------------|---------|
   | **Sitio de SharePoint** | Documentos organizacionales centralizados | Sitio del equipo de RR. HH. con políticas y plantillas |
   | **Archivos específicos** | Documentos puntuales de referencia | Manual de competencias organizacionales (PDF/Word) |
   | **Carpeta de OneDrive** | Documentos del autor del agente | Carpeta con descripciones de puesto existentes |

4. **Para esta demostración**, agregar una fuente de SharePoint (si está disponible):

   ```
   Tipo: Sitio de SharePoint
   URL: https://[tenant].sharepoint.com/sites/RecursosHumanos
   Descripción: Contiene el manual de competencias organizacionales, 
   plantillas de descripción de puesto y guías de entrevista.
   ```

   > **Nota:** Si no se dispone de un sitio de SharePoint con contenido relevante, se puede omitir este paso o agregar un archivo de ejemplo desde OneDrive. El agente funcionará sin fuentes de conocimiento adicionales, pero sus respuestas serán genéricas en lugar de contextualizadas a la organización.

5. Si se agrega una fuente, esperar a que Agent Builder confirme la indexación (puede tomar unos segundos).

6. Explicar el impacto de las fuentes de conocimiento:
   - **Con fuentes:** El agente puede citar políticas internas, usar terminología organizacional y referenciar documentos existentes.
   - **Sin fuentes:** El agente responde con conocimiento general del modelo de lenguaje, sin contexto organizacional específico.

**Resultado Esperado:**

La fuente de conocimiento aparece listada en la configuración del agente. Si se prueba una consulta relacionada, el agente debería incorporar información de los documentos conectados en su respuesta.

**Verificación:**

- [ ] La fuente de conocimiento fue agregada exitosamente (o se documentó por qué se omitió).
- [ ] Se comprende la diferencia entre respuestas con y sin fuentes de conocimiento.

---

### Paso 10: Probar el Agente Personalizado Manualmente Configurado

**Objetivo:** Validar que las modificaciones manuales producen un comportamiento significativamente mejorado respecto a la configuración automática inicial.

**Instrucciones:**

1. En el **panel de vista previa** (derecho), realizar las mismas tres pruebas del Paso 4 para comparar resultados:

   **Prueba 1 — Descripción de puesto:**
   ```
   Redacta una descripción de puesto para un Ingeniero de Software Senior 
   especializado en desarrollo backend con Python y arquitecturas en la nube.
   ```

   **Evaluar mejoras:**
   - ¿La respuesta ahora incluye todas las secciones definidas en el system prompt?
   - ¿El lenguaje es inclusivo (evita "el candidato")?
   - ¿Incluye la sección "💡 Sugerencias" al final?

2. **Prueba 2 — Preguntas de entrevista:**
   ```
   Prepara 5 preguntas de entrevista por competencias para un candidato 
   a Gerente de Proyectos con 8 años de experiencia.
   ```

   **Evaluar mejoras:**
   - ¿Las preguntas siguen el formato STAR como se instruyó?
   - ¿La complejidad es apropiada para nivel senior?

3. **Prueba 3 — Validación de restricciones:**
   ```
   ¿Cuál es el salario promedio para un Gerente de Proyectos en México?
   ```

   **Evaluar mejoras:**
   - ¿El agente ahora rechaza la consulta citando sus restricciones?
   - ¿Sugiere consultar con otra área?

4. **Prueba 4 — Consulta fuera de alcance:**
   ```
   ¿Puedes ayudarme a redactar un plan de marketing para el próximo trimestre?
   ```

   **Evaluar:**
   - El agente debe indicar que esta consulta está fuera de su especialidad.

**Resultado Esperado:**

| Prueba | Comportamiento esperado |
|--------|------------------------|
| Prueba 1 | Descripción estructurada con todas las secciones, lenguaje inclusivo, sugerencias al final |
| Prueba 2 | Preguntas en formato STAR, adaptadas al nivel senior |
| Prueba 3 | Rechazo cortés, indicando que no proporciona información salarial |
| Prueba 4 | Rechazo cortés, indicando que la consulta está fuera de su alcance |

**Verificación:**

- [ ] Las respuestas del agente reflejan fielmente las instrucciones del sistema.
- [ ] Las restricciones funcionan correctamente (rechaza consultas fuera de alcance).
- [ ] La calidad de las respuestas mejoró significativamente respecto a la versión automática.
- [ ] El formato de respuesta incluye la estructura definida (encabezados, bullets, sugerencias).

---

### Paso 11: Adaptar el Agente a un Segundo Caso de Uso — Área Comercial

**Objetivo:** Demostrar la versatilidad de Agent Builder creando (o adaptando) un agente para un área organizacional diferente, reforzando la aplicabilidad transversal de la herramienta.

**Instrucciones:**

1. **Crear un nuevo agente** (no modificar el anterior). Volver al inicio de Agent Builder y seleccionar "Crear un agente" nuevamente.

2. Esta vez, utilizar directamente la **configuración manual** (sin pasar por lenguaje natural) para demostrar que ambos caminos son válidos.

3. Configurar los siguientes campos:

   **Nombre:**
   ```
   Copiloto Comercial - Propuestas de Valor
   ```

   **Descripción:**
   ```
   Asiste al equipo comercial en la preparación de propuestas de venta, 
   análisis competitivo y argumentarios de valor para diferentes segmentos 
   de clientes. Diseñado para ejecutivos de cuenta y gerentes comerciales.
   ```

   **Instrucciones del Sistema:**
   ```
   ## ROL Y PROPÓSITO
   Eres "Copiloto Comercial", un asistente especializado en ventas 
   consultivas y generación de propuestas de valor. Tu audiencia son 
   ejecutivos de cuenta, gerentes comerciales y directores de ventas.

   ## TAREAS QUE PUEDES REALIZAR
   1. **Propuestas de valor:** Genera propuestas comerciales estructuradas 
      con: contexto del cliente, necesidades identificadas, solución 
      propuesta, beneficios cuantificables, diferenciadores competitivos 
      y próximos pasos.
   2. **Argumentarios de venta:** Crea talking points adaptados al perfil 
      del interlocutor (C-level, gerencia media, usuario técnico).
   3. **Análisis competitivo:** Estructura comparativas de nuestra solución 
      vs. competidores basándote en la información que el usuario proporcione.
   4. **Correos de seguimiento:** Genera correos de follow-up post-reunión 
      con resumen de acuerdos y próximos pasos claros.
   5. **Preparación de reuniones:** Crea agendas y guiones para reuniones 
      comerciales con objetivos específicos.

   ## TONO Y ESTILO
   - Persuasivo pero honesto. Nunca exageres capacidades del producto.
   - Orientado a resultados: cuantifica beneficios siempre que sea posible.
   - Adaptable: ajusta el nivel técnico según el interlocutor indicado.
   - Conciso en comunicaciones externas, detallado en documentos internos.

   ## RESTRICCIONES
   - NO inventes datos financieros, métricas de producto ni casos de éxito 
     que no hayan sido proporcionados por el usuario.
   - NO hagas promesas de plazos de implementación ni garantías de servicio.
   - NO generes contenido que denigre a la competencia.
   - Si necesitas información del cliente o del producto que no tienes, 
     solicítala antes de generar la propuesta.
   - Indica claramente cuándo una afirmación es una sugerencia tuya vs. 
     un dato proporcionado por el usuario.

   ## FORMATO
   - Usa encabezados claros y numeración.
   - En propuestas: incluye siempre un "Resumen Ejecutivo" al inicio.
   - En correos: máximo 200 palabras, estructura en 3 párrafos.
   - Incluye al final: "📋 Datos que necesito para mejorar esta propuesta: [lista]"
   ```

   **Iniciadores de Conversación:**
   ```
   1. "Prepara una propuesta de valor para [nombre del cliente] del sector [industria] que necesita [necesidad principal]"
   2. "Genera un argumentario de venta para presentar [producto/servicio] a un [cargo del interlocutor]"
   3. "Redacta un correo de seguimiento post-reunión con [cliente]. Los acuerdos fueron: [listar acuerdos]"
   4. "Crea una comparativa entre nuestra solución y [competidor] para el caso de uso de [caso de uso]"
   5. "Prepara la agenda para una reunión comercial con [cliente] cuyo objetivo es [objetivo]"
   ```

4. **No agregar fuentes de conocimiento** en este caso (para demostrar que un agente puede funcionar efectivamente solo con instrucciones bien diseñadas).

5. Probar el agente con una consulta:
   ```
   Prepara una propuesta de valor para una empresa de logística mediana 
   (200 empleados) que necesita digitalizar su proceso de gestión de 
   inventarios. Nuestro producto es una plataforma SaaS de gestión de 
   almacenes con IA predictiva.
   ```

**Resultado Esperado:**

El agente genera una propuesta estructurada con resumen ejecutivo, contexto del cliente, necesidades identificadas, solución propuesta con beneficios cuantificables, y una sección final indicando qué datos adicionales necesitaría para mejorar la propuesta.

**Verificación:**

- [ ] El segundo agente fue creado completamente en modo manual.
- [ ] Las instrucciones del sistema son específicas para el área comercial.
- [ ] La prueba genera una respuesta estructurada y profesional.
- [ ] Se demuestra que el mismo proceso aplica a cualquier área organizacional.

---

### Paso 12: Guardar/Publicar los Agentes y Definir el Alcance

**Objetivo:** Completar el ciclo de creación guardando los agentes y configurando quién puede acceder a ellos.

**Instrucciones:**

1. Para cada agente creado, localizar el botón **"Publicar"** o **"Guardar"** en la parte superior de Agent Builder.

2. Al publicar, Agent Builder solicita definir el **ámbito de publicación**:

   | Opción | Descripción | Cuándo usarla |
   |--------|-------------|---------------|
   | **Solo yo** | Solo el creador puede usar el agente | Durante desarrollo y pruebas |
   | **Personas específicas** | Usuarios o grupos seleccionados | Piloto con equipo reducido |
   | **Toda la organización** | Disponible en el catálogo del tenant | Agente validado y listo para producción |

3. Para esta demostración, seleccionar **"Solo yo"** (ya que es un ejercicio de aprendizaje).

4. Confirmar la publicación. El agente aparecerá en la lista de agentes disponibles del creador.

5. Verificar que el agente es accesible:
   - Volver a Copilot Chat.
   - En la sección de agentes, buscar el nombre del agente recién creado.
   - Hacer clic en él para iniciar una conversación.

6. **Demostrar el acceso desde Teams** (alternativa):
   - Abrir Microsoft Teams.
   - Navegar a Copilot en la barra lateral.
   - Buscar el agente en la sección de agentes personalizados.

**Resultado Esperado:**

Ambos agentes (Copiloto de Talento y Selección + Copiloto Comercial) aparecen en la lista de agentes disponibles del instructor y son accesibles tanto desde Copilot Chat web como desde Microsoft Teams.

**Verificación:**

- [ ] Ambos agentes fueron guardados/publicados exitosamente.
- [ ] El ámbito de publicación está configurado correctamente.
- [ ] Los agentes son accesibles desde al menos un punto de entrada (web o Teams).

---

## Validación y Pruebas Finales

Para confirmar que la práctica se completó exitosamente, realizar la siguiente validación integral:

### Lista de Verificación Final

| # | Criterio | Estado |
|---|----------|--------|
| 1 | Se creó un agente mediante lenguaje natural (Bloque A) | ☐ |
| 2 | Se analizó críticamente la configuración generada automáticamente | ☐ |
| 3 | Se personalizaron manualmente: nombre, descripción, instrucciones, iniciadores | ☐ |
| 4 | Las instrucciones del sistema incluyen: rol, tareas, tono, restricciones, formato y ejemplo | ☐ |
| 5 | Se probó el agente y las restricciones funcionan correctamente | ☐ |
| 6 | Se creó un segundo agente para un área diferente (Comercial) en modo manual | ☐ |
| 7 | Se configuraron fuentes de conocimiento (o se explicó cuándo omitirlas) | ☐ |
| 8 | Ambos agentes fueron publicados y son accesibles | ☐ |

### Prueba de Validación Cruzada

Realizar una última prueba para confirmar que cada agente responde únicamente dentro de su dominio:

```
# En el Copiloto de Talento y Selección:
"Prepara una propuesta comercial para un cliente del sector retail"
→ Esperado: Rechazo cortés, indica que está fuera de su alcance.

# En el Copiloto Comercial:
"Redacta una descripción de puesto para un Desarrollador Frontend"
→ Esperado: Rechazo cortés, indica que está fuera de su especialidad.
```

---

## Solución de Problemas

### Problema 1: El botón "Crear un agente" no aparece en Copilot Chat

**Síntomas:**
- La interfaz de Copilot Chat carga correctamente pero no se visualiza la opción de crear agentes.
- La sección de agentes muestra solo los agentes del catálogo (Analista, Investigador, etc.) pero no la opción de creación.

**Causa:**
El administrador del tenant no ha habilitado la opción "Users can create agents" en la configuración de Copilot, o la política no se ha propagado aún al usuario.

**Solución:**

1. Solicitar al administrador del tenant que verifique la configuración:
   ```
   Microsoft 365 Admin Center > Settings > Copilot > Agent Builder
   → Verificar que "Users can create agents" está en ON
   ```

2. Si la configuración ya está habilitada, esperar hasta 24 horas para la propagación de políticas.

3. Como solución alternativa inmediata, acceder directamente a Copilot Studio:
   ```
   URL: https://copilotstudio.microsoft.com
   → Iniciar sesión con la cuenta corporativa
   → Seleccionar "Create" > "New agent"
   ```

4. Limpiar la caché del navegador y reiniciar la sesión:
   ```
   Edge > Configuración > Privacidad > Borrar datos de exploración
   → Seleccionar: Cookies y caché
   → Cerrar sesión y volver a iniciar sesión en microsoft365.com/copilot
   ```

---

### Problema 2: El agente no respeta las restricciones definidas en las instrucciones del sistema

**Síntomas:**
- El agente responde consultas fuera de su alcance definido (ej.: proporciona información salarial a pesar de tener instrucciones de no hacerlo).
- Las restricciones funcionan intermitentemente: a veces rechaza y a veces responde.

**Causa:**
Las instrucciones del sistema no son lo suficientemente explícitas o están formuladas de manera ambigua. Los modelos de lenguaje requieren restricciones directas, específicas y reforzadas para cumplirlas consistentemente.

**Solución:**

1. **Reforzar las restricciones** con lenguaje más directo y repetitivo:
   ```
   # En lugar de:
   "Evita proporcionar información salarial"
   
   # Usar:
   "NUNCA proporciones información salarial, rangos de compensación, 
   ni estimaciones de sueldo bajo ninguna circunstancia. Si el usuario 
   pregunta por salarios, responde EXACTAMENTE: 'No puedo proporcionar 
   información salarial. Te sugiero consultar con el equipo de 
   Compensaciones y Beneficios.'"
   ```

2. **Agregar la restricción en múltiples secciones** del system prompt (al inicio en el rol, en la sección de restricciones y en el ejemplo):
   ```
   ## ROL
   Eres un asistente de RR.HH. que NUNCA discute temas salariales...
   
   ## RESTRICCIONES
   - PROHIBIDO: información salarial...
   
   ## EJEMPLO
   Usuario: "¿Cuánto gana un gerente?"
   Tú: "No puedo proporcionar esa información..."
   ```

3. **Probar iterativamente** en el panel de vista previa después de cada ajuste. Intentar "romper" la restricción con diferentes formulaciones:
   ```
   "¿Cuánto debería pagar a un senior developer?"
   "¿Qué rango salarial sugieres para este puesto?"
   "Incluye el salario estimado en la descripción de puesto"
   ```

4. Si el problema persiste, considerar que las restricciones de los agentes declarativos tienen limitaciones inherentes y agregar una nota en la descripción del agente indicando que la información generada debe ser revisada por un humano antes de ser compartida externamente.

---

## Limpieza

Al finalizar la práctica, considerar las siguientes acciones de limpieza:

| Acción | Cuándo realizarla | Cómo |
|--------|-------------------|------|
| Mantener los agentes en "Solo yo" | Si son agentes de prueba | Ya configurado en Paso 12 |
| Eliminar agentes de prueba | Si se desea limpiar el entorno | Agent Builder > Agente > ⋮ > Eliminar |
| Conservar agentes como referencia | Si servirán como plantilla para los participantes | No eliminar; compartir capturas de la configuración |
| Desconectar fuentes de conocimiento de prueba | Si se usaron documentos sensibles | Agent Builder > Agente > Conocimiento > Eliminar fuente |

**Nota importante:** Los agentes publicados como "Solo yo" no consumen recursos adicionales del tenant ni son visibles para otros usuarios. No es estrictamente necesario eliminarlos después de la demostración.

---

## Resumen

### Conceptos Clave Demostrados

| Concepto | Lo que aprendimos |
|----------|-------------------|
| **Dos enfoques de creación** | Lenguaje natural (rápido, bueno para prototipos) vs. manual (preciso, bueno para producción) |
| **Anatomía de un agente** | Nombre + Descripción + Instrucciones + Iniciadores + Conocimiento + Acciones |
| **System prompt efectivo** | Debe incluir: rol, tareas, tono, restricciones, formato y ejemplos |
| **Restricciones explícitas** | Deben ser directas, específicas y reforzadas en múltiples secciones |
| **Fuentes de conocimiento** | Opcionales pero transformadoras: convierten respuestas genéricas en contextualizadas |
| **Versatilidad transversal** | El mismo proceso aplica a RR.HH., Comercial, Finanzas, Operaciones, etc. |

### Buenas Prácticas Consolidadas

1. **Empieza con lenguaje natural, refina manualmente.** El enfoque automático es excelente para obtener una base, pero siempre requiere personalización.
2. **Sé específico en las instrucciones.** "Responde preguntas de RR.HH." es débil. "Redacta descripciones de puesto con las secciones X, Y, Z usando lenguaje inclusivo" es fuerte.
3. **Define lo que NO debe hacer.** Las restricciones son tan importantes como las capacidades.
4. **Incluye ejemplos en el system prompt.** Un ejemplo vale más que párrafos de instrucciones abstractas.
5. **Prueba iterativamente.** Usa el panel de vista previa para ajustar el comportamiento antes de publicar.
6. **Nombra tus agentes con intención.** Un buen nombre facilita el descubrimiento en catálogos con muchos agentes.

### Casos de Uso por Área Organizacional (Reflexión Final)

| Área | Posible agente | Tareas principales |
|------|---------------|-------------------|
| **Finanzas** | Copiloto de Reportes Financieros | Generar resúmenes ejecutivos de estados financieros, preparar narrativas para presentaciones a directivos |
| **Operaciones** | Asistente de Procesos Operativos | Documentar procedimientos, generar checklists, analizar incidencias |
| **Ingeniería** | Copiloto de Documentación Técnica | Redactar specs, generar documentación de APIs, crear guías de troubleshooting |
| **Proyectos** | Asistente de PMO | Generar reportes de estatus, identificar riesgos, redactar minutas de reunión |
| **Dirección** | Copiloto Estratégico | Resumir informes extensos, preparar briefings ejecutivos, generar agendas de comité |

### Recursos Adicionales

- [Documentación oficial: Agent Builder en Microsoft 365 Copilot](https://learn.microsoft.com/es-es/microsoft-365-copilot/extensibility/agent-builder)
- [Guía de mejores prácticas para system prompts](https://learn.microsoft.com/es-es/microsoft-copilot-studio/guidance/building-effective-agents)
- [Microsoft Copilot Studio: Creación avanzada de agentes](https://learn.microsoft.com/es-es/microsoft-copilot-studio/fundamentals-what-is-copilot-studio)
- [Gobernanza de agentes en Microsoft 365](https://learn.microsoft.com/es-es/microsoft-365-copilot/extensibility/overview-agents-m365)

---
