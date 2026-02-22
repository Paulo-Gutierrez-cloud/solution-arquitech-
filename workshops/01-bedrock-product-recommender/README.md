# Workshop 01: Product Recommendation Chatbot with Amazon Bedrock Agents

<p align="center">
  <img src="./assets/image1.png" width="800" alt="Workshop Title" />
</p>

## 📋 Resumen Ejecutivo
En este workshop, implementé un **Agente de Amazon Bedrock** diseñado para aplicaciones de e-commerce. Este agente utiliza modelos de lenguaje (LLMs) para interactuar con clientes, entender sus necesidades y recomendar productos de forma dinámica consumiendo APIs reales.

---

## 🏗️ Arquitectura de la Solución
La solución utiliza una arquitectura **Serverless** que integra capacidades de IA con servicios tradicionales de AWS.

```mermaid
graph TD
    User([Usuario/App]) <-->|Natural Language| Agent[Amazon Bedrock Agent]
    
    subgraph "Inteligencia y Orquestación"
        Agent <-->|Invoca| Lambda[AWS Lambda Action Groups]
        Agent <-->|RAG| KB[Knowledge Base for Bedrock]
    end
    
    subgraph "Datos y Contenido"
        Lambda <-->|Query| DDB[(Amazon DynamoDB Catálogo)]
        KB <-->|Ingesta| S3[Amazon S3 Docs]
        Agent -- "Upselling" --> Pers[Personalize API]
    end

    style Agent fill:#FF9900,stroke:#232F3E,stroke-width:2px,color:#fff
    style Lambda fill:#FF9900,stroke:#232F3E,stroke-width:1px,color:#fff
    style KB fill:#FF9900,stroke:#232F3E,stroke-width:1px,color:#fff
```

---

## 🛠️ Servicios Utilizados
- **Amazon Bedrock Agents**: Para la orquestación de la conversación y razonamiento.
- **AWS Lambda**: Para ejecutar la lógica de negocio (consultar productos).
- **Amazon DynamoDB**: Almacenamiento NoSQL escalable para el stock de productos.
- **Amazon S3 + Knowledge Bases**: Para implementar RAG (acceso a información técnica de productos).
- **Amazon Personalize**: Para sugerencias personalizadas de "venta cruzada".

---

## 📸 Evidencia de Implementación

### 1. Configuración del Agente
Se definieron las instrucciones del sistema y se seleccionó el modelo fundacional (Claude).
<p align="center">
  <img src="./assets/image30.png" width="700" alt="Agent Configuration" />
</p>

### 2. Trazabilidad y Razonamiento (Orchestration Trace)
Aquí se observa cómo el agente "piensa" y decide qué API llamar basándose en la charla con el usuario.
<p align="center">
  <img src="./assets/image10.png" width="700" alt="Orchestration Trace" />
</p>

### 3. Resultados Finales
El agente es capaz de gestionar carritos y recomendar productos con precisión.
<p align="center">
  <img src="./assets/image38.png" width="700" alt="Workshop Summary" />
</p>

---

## 💡 Key Takeaways
- **Generative AI Agents**: Aprendí a pasar de un modelo estático a un agente proactivo que ejecuta acciones.
- **RAG (Retrieval Augmented Generation)**: Implementación de conocimiento externo sin re-entrenar el modelo.
- **Multi-Agent Collaboration**: Uso de agentes especializados trabajando en conjunto para una tarea compleja.

---
*Este proyecto forma parte de mi portafolio impulsado por la beca de Solution Architect.*
