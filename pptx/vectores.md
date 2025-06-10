---
marp: true
theme: default
class: lead
paginate: true
backgroundColor: #0a0f1c
color: #ffffff
style: |
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap');
  
  section {
    background: linear-gradient(135deg, #0a0f1c 0%, #1e1b4b 50%, #0a0f1c 100%);
    font-family: 'Inter', sans-serif;
    padding: 60px;
    font-size: 24px;
    line-height: 1.4;
  }
  
  h1 {
    font-size: 50px;
    font-weight: 800;
    background: linear-gradient(135deg, #60a5fa 0%, #a78bfa 50%, #f472b6 100%);
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    text-align: center;
    margin-bottom: 40px;
    line-height: 1.1;
  }
  
  h2 {
    font-size: 40px;
    font-weight: 700;
    color: #60a5fa;
    margin-bottom: 40px;
    border-bottom: 4px solid #3b82f6;
    padding-bottom: 20px;
    line-height: 1.2;
  }
  
  h3 {
    font-size: 36px;
    font-weight: 600;
    color: #a78bfa;
    margin-bottom: 30px;
    line-height: 1.3;
  }
  
  .columns {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 60px;
    margin: 40px 0;
  }
  
  .story-box {
    background: linear-gradient(135deg, rgba(59, 130, 246, 0.1), rgba(167, 139, 250, 0.1));
    border: 3px solid #3b82f6;
    border-radius: 20px;
    margin: 40px 0;
    font-size: 28px;
    text-align: center;
    line-height: 1.5;
  }
  
  .concept-card {
    background: linear-gradient(135deg, rgba(34, 197, 94, 0.15), rgba(59, 130, 246, 0.15));
    border-left: 8px solid #22c55e;
    margin: 40px 0;
    border-radius: 0 20px 20px 0;
    font-size: 26px;
  }
  
  .problem-box {
    background: linear-gradient(135deg, rgba(239, 68, 68, 0.1), rgba(251, 191, 36, 0.1));
    border: 3px solid #ef4444;
    border-radius: 20px;
    padding: 5px;
    margin: 20px 0;
    text-align: center;
    font-size: 36px;
  }
  
  .solution-box {
    background: linear-gradient(135deg, rgba(34, 197, 94, 0.15), rgba(16, 185, 129, 0.15));
    border: 3px solid #10b981;
    border-radius: 20px;
    margin: 20px 0;
    text-align: center;
    font-size: 26px;
  }
  
  .example-simple {
    background: #1a1a2e;
    border-left: 6px solid #f59e0b;
    padding: 40px;
    margin: 40px 0;
    border-radius: 0 15px 15px 0;
    font-family: monospace;
    font-size: 22px;
  }
  
  .big-number {
    font-size: 80px;
    font-weight: 800;
    color: #3b82f6;
    text-align: center;
    margin: 30px 0;
    line-height: 1;
  }
  
  .highlight {
    background: linear-gradient(135deg, #fbbf24, #f59e0b);
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    font-weight: 700;
  }
  
  .success { color: #22c55e; font-weight: 600; }
  .warning { color: #f59e0b; font-weight: 600; }
  .error { color: #ef4444; font-weight: 600; }
  
  .subtitle {
    font-size: 32px;
    color: #94a3b8;
    text-align: center;
    margin-bottom: 50px;
    font-weight: 400;
    line-height: 1.4;
  }
  
  .center { text-align: center; }
  
  ul {
    list-style: none;
    padding: 0;
    margin: 40px 0;
  }
  
  li {

    position: relative;
    font-size: 20px;
    line-height: 1.4;
  }
  
  li::before {
    content: "➤";
    color: #3b82f6;
    left: 0;
    font-weight: bold;
    font-size: 20px;
  }
  
  .emoji {
    font-size: 30px;
    margin: 20px 0;
    display: block;
  }
  
  p {
    font-size: 28px;
    line-height: 1.5;
    margin: 20px 0;
  }
  
  strong {
    font-weight: 600;
    color: #ffffff;
  }
---

# 🧠 **¿Qué son los Embeddings?**
## **La Revolución Silenciosa que está Transformando la IA**

<div class="subtitle">De Palabras a Números: Cómo las Máquinas Entienden el Lenguaje Humano</div>

---

## 🤔 **La Historia Comienza con un Problema...**

<div class="problem-box">

### **Imagina que eres una computadora** 🤖

**¿Cómo entenderías estas palabras?**
- "Rey"
- "Reina" 
- "Hombre"
- "Mujer"

**Para ti son solo letras... ¡No tienen significado!**

</div>

<div class="center">
<div class="big-number">🤷‍♂️</div>
<h3>Las computadoras no entienden palabras... ¡solo números!</h3>
</div>

---

## ✨ **Entonces llegan los Embeddings...**

<div class="solution-box">

### **Los Embeddings son la <span class="highlight">traducción mágica</span>**

**Convierten palabras en vectores (listas de números) que las máquinas SÍ pueden entender**

</div>

<div class="columns">
<div>

### **Antes (Texto):**
- "Rey" = ???
- "Reina" = ??? 
- "Perro" = ???

</div>
<div>

### **Después (Vectores):**
- "Rey" = [0.2, -0.8, 0.5, ...]
- "Reina" = [0.3, -0.7, 0.4, ...]
- "Perro" = [-0.1, 0.2, -0.9, ...]

</div>
</div>

<div class="center">
<h3>🎯 <span class="success">¡Ahora la IA puede "entender" las relaciones!</span></h3>
</div>

---

## 🧩 **La Magia de las Relaciones Semánticas**

<div class="story-box">

### **¿Qué hace especiales a los embeddings?**

**Las palabras similares tienen vectores similares**

</div>

<div class="columns">
<div>

### **👑 Realeza:**
- Rey: [0.8, 0.2, 0.1]
- Reina: [0.7, 0.3, 0.1]
- Príncipe: [0.6, 0.2, 0.2]

**¡Están cerca en el espacio vectorial!**

</div>
<div>

### **🐕 Animales:**
- Perro: [0.1, 0.8, 0.3]
- Gato: [0.2, 0.7, 0.4]
- León: [0.3, 0.6, 0.5]

**¡También están agrupados!**

</div>
</div>

<div class="center">
<div class="emoji">🤯</div>
<h3>¡La IA descubre relaciones que nosotros ni sabíamos!</h3>
</div>

---

## 📊 **El Álgebra Mágica de las Palabras**

<div class="concept-card">

### **La ecuación más famosa de la IA:**

<div class="center">
<div class="big-number">👑 - 👨 + 👩 = 👸</div>
<h3>Rey - Hombre + Mujer = Reina</h3>
</div>

**¡Los embeddings pueden hacer matemáticas con conceptos!**

</div>

### **¿Cómo es posible esto?**

Los embeddings capturan **relaciones semánticas** de manera que:
- "Rey" tiene la relación "masculino" con "Reina"
- Si quitamos "masculino" y agregamos "femenino"
- ¡Obtenemos "Reina"!

---

## 🌍 **¿Por qué Importa en el Mundo Real?**

<div class="columns">
<div>

### **❌ Búsqueda Tradicional:**
**Usuario busca:** "problemas de rendimiento"

**Sistema encuentra:** Solo documentos con esas palabras exactas

**Se pierde:** "lentitud", "bajo desempeño", "optimización"

</div>
<div>

### **✅ Búsqueda con Embeddings:**
**Usuario busca:** "problemas de rendimiento"

**Sistema encuentra:** Todo lo relacionado semánticamente

**Incluye:** "lentitud", "lag", "bottleneck", "optimization"

</div>
</div>

<div class="center">
<h3>🎯 <span class="success">¡10x más resultados relevantes!</span></h3>
</div>

---

## 🏢 **Casos de Uso Empresariales Reales**

<div class="columns">
<div>

### **🛒 E-commerce**
**Cliente busca:** "zapatos para correr"
**Encuentra:** sneakers, running shoes, calzado deportivo


</div>
<div>

### **⚖️ Legal**
**Abogado busca:** "contrato de arrendamiento"
**Encuentra:** acuerdo de renta, lease agreement



</div>
</div>

<div class="center">
<h3>💡 <span class="highlight">¡La IA entiende el contexto como un humano!</span></h3>
</div>

---

## 📈 **Los Números que Impresionan**

<div class="columns">
<div>

<div class="concept-card">
<div class="center">
<div class="big-number">85%</div>
<h3>Mejora en precisión de búsqueda</h3>
</div>
</div>

<div class="concept-card">
<div class="center">
<div class="big-number">70%</div>
<h3>Reducción en tiempo de búsqueda</h3>
</div>
</div>

</div>
<div>

<div class="concept-card">
<div class="center">
<div class="big-number">50+</div>
<h3>Idiomas soportados</h3>
</div>
</div>

<div class="concept-card">
<div class="center">
<div class="big-number">24/7</div>
<h3>Disponibilidad del sistema</h3>
</div>
</div>

</div>
</div>

---

## 🎯 **¿Dónde Guardamos Todos Estos Vectores?**

<div class="columns">
<div>

### **🏠 Para Proyectos Pequeños:**
- **ChromaDB**: Fácil de usar
- **FAISS**: Súper rápido localmente

### **🏢 Para Empresas:**
- **Pinecone**: En la nube, sin complicaciones
- **Weaviate**: Potente y flexible

</div>
<div>

### **🚀 Integraciones :**
- **Postgres**: pgVector
- **Mongose**: MongoDB Atlas

### **⚡ Lo que Necesitas Saber:**
- Más vectores = Más memoria
- Más consultas = Más CPU
- Más precisión = Más tiempo

</div>
</div>

---

###  **¿Cómo se Construye un Sistema de Embeddings?**


#### **Paso 1: Preparar los Datos** 
Tomar documentos y dividirlos en pedazos pequeños

#### **Paso 2: Crear Embeddings** 
Convertir cada pedazo en vectores usando IA

#### **Paso 3: Almacenar** 
Guardar vectores en una base de datos especializada

#### **Paso 4: Buscar** 
Cuando llega una consulta, encontrar vectores similares

#### **Paso 5: Responder** 
Devolver los documentos más relevantes

---

## 🌟 **La Diferencia Entre Bueno y Excelente**

<div class="columns">
<div>

### **😐 Sistema Básico:**
- Búsqueda solo por palabras
- Resultados limitados
- No entiende contexto
- Un solo idioma

</div>
<div>

### **🚀 Sistema con Embeddings:**
- Búsqueda semántica
- Resultados comprensivos
- Entiende intención
- Multiidioma natural

</div>
</div>

<div class="center">
<div class="emoji">⭐</div>
<h3><span class="success">Los embeddings son la diferencia entre buscar y ENCONTRAR</span></h3>
</div>

---

## 🔮 **El Futuro ya está Aquí**

<div class="concept-card">

### **Lo que viene en 2025-2026:**

- **Búsqueda multimodal**: Texto + Imágenes + Audio + Video
- **IA que aprende**: Sistemas que mejoran automáticamente
- **Tiempo real**: Actualizaciones instantáneas
- **Personalización**: Cada usuario tiene su propia experiencia

</div>

<div class="center">
<div class="emoji">🚀</div>
<h3>¡Y todo empieza con entender los embeddings!</h3>
</div>


---

### 🎓 **¿Qué Aprenderemos Hoy?**

#### **Módulo 1: Fundamentos** 
Cómo funcionan realmente los embeddings

#### **Módulo 2: Implementación** 
Construir tu primer sistema paso a paso busqueda en archivo pdf

#### **Módulo 3: Escalar** 
Constuir un sistema de búsqueda escalable y eficiente, usando un herramientas de las longchain

#### **Módulo 4: Ingregar con una base datos**
Constuir un sistema de búsqueda en basedatos de vectores



---

![bg left width:100%](../img/image.png)



Los algoritmos ANN son la clave para la búsqueda de similitud a gran escala en bases de datos vectoriales.
En lugar de encontrar el "vecino más cercano" exacto (que es computacionalmente costoso), los ANN encuentran una aproximación muy cercana en una fracción del tiempo.

---


Aquí tienes una diapositiva que explica cómo funcionan los algoritmos de Vecinos Más Cercanos Aproximados (ANN) en las bases de datos vectoriales para una búsqueda eficiente:

---

## **Búsqueda Eficiente de Documentos: Algoritmos ANN en Bases de Datos Vectoriales**

---


**¿Cómo Funcionan (Principios Clave)?**

- Indexación Inteligente:
    
- Compromiso entre Precisión y Velocidad:
   
- Técnicas Comunes:
    * Basados en Gráficos (ej. HNSW - Hierarchical Navigable Small World)
    * Basados en Árboles (ej. KD-Trees, ANNOY):
    * Basados en Hashing (ej. LSH - Locality Sensitive Hashing):
    * Basados en Agrupamiento (ej. FAISS):


---

![alt text](image.png)


---

# 🎯 **¿Preguntas Antes de Empezar?**

<div class="center">
<div class="emoji">🤔</div>

### **Recuerda: No hay preguntas tontas**
### **Solo oportunidades para aprender más**

<div class="story-box">
<h3>🚀 Próximo: Vamos a ver esto en acción con ejemplos reales</h3>
</div>
</div>