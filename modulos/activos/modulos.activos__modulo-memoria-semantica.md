---
rol: ModuloMemoriaSemanticaGPT
versión: 1.0.0
autoridad: GPT_P39_Central
estado: activo
sincronizado_con:
  - memoria-viva-ext.v3.md
  - estrategia_grabado_consulta_memoria.md
---

# 🧠 Módulo de Memoria Semántica — Palma39

> Este módulo describe el mecanismo de análisis semántico y razonamiento basado en similitud contextual que complementa la memoria simbólica estructurada.

---

## 🎯 Objetivo

Permitir a los GPTs de Palma39 **recuperar aprendizajes o soluciones similares** a partir de contexto semántico, no solo coincidencias literales o exactas.

---

## 🧬 Descripción técnica

La memoria semántica trabaja con **embeddings** y **modelos de vectorización del conocimiento**. Esto permite comparar:

- Conceptos que se expresan con diferente sintaxis pero misma intención.
- Casos que no coinciden literal, pero tienen estructura o propósito análogo.
- Intenciones del usuario con soluciones previamente aprendidas.

---

## 🔍 Flujo de uso

1. El GPT extrae las keywords del contexto actual.
2. Calcula embedding del concepto o pregunta.
3. Lanza una búsqueda vectorial contra un índice (ej. Supabase + pgvector o Weaviate).
4. Recupera registros similares (con un umbral de similitud ajustable).
5. Compara resultados con memoria estructurada (`GetMemory()`).
6. Fusiona o prioriza según criterio de confianza y MAI.

---

## 📚 Casos de uso

- Detectar si ya se resolvió un caso "similar" aunque tenga distinto título.
- Aprender sinónimos técnicos o soluciones alternativas.
- Recomendar aprendizajes antiguos en nuevas conversaciones.

---

## 🧠 Parámetros configurables

- Similaridad mínima (`similarity_threshold`, ej. 0.75)
- Cantidad de resultados (`top_k`, ej. 5)
- Campos del embedding (`descripcion`, `solucion`, `resumen_narrativo`)
- Vector DB externo o incrustado (Supabase, Pinecone, etc.)

---

## 🤖 GPTs que lo usan

- `EvaluadorGPT`
- `ComparadorGPT`
- `CriticoGPT`

---

## 📌 Frase guía

> “No busques solo lo igual. Busca lo que rime en intención, aunque cambie de forma.”