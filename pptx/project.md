---
marp: true
theme: default
class: invert
paginate: true
backgroundColor: #1a1a2e
color: #ffffff
style: |
  .columns {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
  .columns-3 {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 1rem;
  }
  .highlight {
    background: linear-gradient(45deg, #667eea 0%, #764ba2 100%);
    padding: 1rem;
    border-radius: 10px;
    margin: 1rem 0;
  }
  .code-block {
    background: #2d3748;
    border-left: 4px solid #667eea;
    padding: 1rem;
    margin: 1rem 0;
    font-size: 0.8em;
  }
  .warning {
    background: linear-gradient(45deg, #ff6b6b 0%, #ee5a52 100%);
    padding: 1rem;
    border-radius: 10px;
    margin: 1rem 0;
  }
  .success {
    background: linear-gradient(45deg, #51cf66 0%, #37b24d 100%);
    padding: 1rem;
    border-radius: 10px;
    margin: 1rem 0;
  }
  section {
    background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
  }
  h1, h2 {
    color: #667eea;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
  }
  .emoji {
    font-size: 1.5em;
  }
  .img {
    max-width: 100%;
    height: auto;
  }
  .img-center {
    display: block;
    margin-left: auto;
    margin-right: auto;
  }
  .img-responsive {
    max-width: 100%;
    height: auto;
  }
---

# 🧠 Agentes AI y Agentic RAG  
**Arquitectura, componentes y metodología detallada**

---

## 1. ¿Qué es un agente AI?

- Un **agente AI** es un sistema autónomo que:
  - **Percibe** el entorno mediante entradas (texto, APIs, sensores).
  - **Planifica** estrategias para resolver tareas.
  - **Actúa** usando herramientas (LLM, API, web, buscadores).
  - **Aprende y memoriza** para mejorar con el tiempo.
- Autonomía gradual: de respuestas simples hasta pensamiento secuencial multi-paso.
- Ejemplo popular: **ReAct** (Reactive + Reasoning) donde el agente razona, actúa, observa y repite 

---

## 2. Componentes esenciales de un agente

| Componente         | Función clave |
|--------------------|---------------|
| **Percepción**     | Interpreta inputs: texto, APIs, documentos  |
| **Razonamiento/Decisión** | Analiza, compara rutas de acción (ReAct, BDI)  |
| **Planificación**  | Divide tareas complejas en subtareas secuenciales : |
| **Acción / Ejecución** | Utiliza herramientas: web buscador, vectorDB, APIs |
| **Memoria**        | Retiene contexto, episodios, histórico de conversación  |
| **Aprendizaje**    | Ajusta comportamiento según experiencia (RL, ML)  |


---

## 4. Arquitectura de Agentic RAG

1. **Agente** actúa como **orquestador** del pipeline RAG.
2. En la etapa de **retrieval**: el agente selecciona entre herramientas: vectorDB, web search, API, calculadora, etc
3. **Iteración lógica**:
   - El agente recupera documentos.
   - Evalúa relevancia.
   - Refina la consulta según resultados.
   - Ramifica decisiones según calidad de la información .  
4. Puede extenderse a multi-agentes (**MA‑RAG**): Planner, Extractor, QA Agents colaboran en cadenas de pensamiento

---

## 5. Flujos y ciclos comunes

### ReAct → RAG → Agentic RAG

1. **ReAct**: razonamiento y acción secuencial (pensamiento + herramienta + observación).
2. **RAG tradicional**: recuperación seguida de generación sin control lógico.
3. **Agentic RAG**: recuperación activa + refinamiento + acción + generación interactiva :contentReference[oaicite:16]{index=16}.

### Ciclo Maker–Checker (Microsoft/Swyftask):
- Planificación → Tool call → Check → Refine → Re-plan → Respuesta.

---

## 6. Metodología paso a paso para construir tu agente (como en tu flujo RAG de aduanas)

1. **Carga y preprocesa** documentos → split & embed.
2. **Indexa** con vectorDB + herramientas.
3. Define componentes de agente:
   - Decidir cuándo recuperar y con qué herramienta.
   - Evaluar relevancia (grader).
   - Refinar preguntas (rewrite).
   - Responder (generate).
4. **Orquesta** con un grafo de estados (LangGraph, StateGraph).
5. **Itera**: refina el prompt, evalúa contexto, responde.
6. Puedes escalar a **multi-agentes colaborativos** (planner, extractor, QA).

---

## 🧠 LangChain

**🔧 Ideal para:**
- Prototipos rápidos
- Integrar LLMs con funciones
- Procesos lineales o simples con decisiones



---

## 🔀 ¿Qué es LangGraph?

- **Extensión sobre LangChain** para representar flujos como **grafos de estado**.
- Permite:
  - Nodos (acciones, herramientas, funciones)
  - Transiciones condicionales
  - Bucles y ramificaciones
- Es una **orquestación visual y dinámica** para agentes complejos

**📊 Ideal para:**
- Sistemas interactivos
- Agentes con lógica iterativa
- Decisiones múltiples y flujo no lineal

---


## ⚖️ Comparación directa

| Característica             | LangChain                          | LangGraph                                 |
|----------------------------|------------------------------------|-------------------------------------------|
| 🔁 Flujo de ejecución      | Lineal (Chains)                    | Grafo de estados dinámico (Nodes + Edges) |
| 🧠 Agentes                 | Soportados                         | Soportados y extendidos                   |
| 🔀 Ramas y bucles          | Limitados                          | Nativo                                    |
| 🧩 Modularidad visual      | Parcial                            | Total (cada nodo representa una acción)   |
| 🧪 Casos ideales           | Procesos simples o secuenciales    | Lógica condicional, agentes avanzados     |
---


![alt text](<Screenshot From 2025-06-12 13-27-05.png>)

---


## 7. Ventajas y beneficios

- ✔️ Respuestas **más precisas** y con contexto real‑time.
- ✔️ Menos **alucinaciones** gracias a recuperación activa.
- ✔️ **Flexibilidad**: el agente selecciona herramientas según el dominio.
- ✔️ **Escalable**: útil en dominios regulatorios, atención, salud, finanzas, etc. .

---

## 8. Retos y consideraciones

- 🔐 **Gobernanza y transparencia**: el agente debe explicar decisiones.
- ⚖️ **Sesgos y control ético**: especialmente en dominios sensibles.
- 🛠️ **Rendimiento**: iteraciones múltiples incrementan costo; se equilibran precisión y eficiencia.
- 🤝 **Coordinación multi‑agente**: necesaria en sistemas colaborativos tipo MA‑RAG

---

## 9. Resumen final

- Un **agente AI** integra:
  - Percepción → Razonamiento → Planificación → Acción → Memoria → Aprendizaje.
- **RAG** añade recuperación de contexto antes de la generación.
- **Agentic RAG** eleva el proceso: el agente **decide**, **elegir** herramientas, **refina** iterativamente y **colabora** multi‑agentes.
- Tu proyecto de aduanas ya implementa las piezas clave: loader, splitter, retriever, grader, rewrite, grafo de estado.
- La evolución siguiente: añadir **planificador explícito**, orquestación multi‑agente y gobernanza.

---