---
rol: ModuloInteligenciaColectivaGPT
versión: 1.0.0
autoridad: GPT_P39_Central
estado: activo
sincronizado_con:
  - memoria-viva-ext.v3.md
  - estrategia_grabado_consulta_memoria.md
  - registro-aprendizaje.md
---

# 🧠 Módulo de Inteligencia Colectiva GPT — Palma39

> Define la lógica que permite a varios GPTs colaborar, razonar, validar y construir conocimiento conjunto dentro del ecosistema Palma39.

---

## 🎯 Objetivo

Permitir coordinación cognitiva entre GPTs especializados para:

- Validar decisiones de forma colaborativa.
- Razonar desde múltiples perspectivas.
- Construir aprendizaje grupal distribuido.
- Prevenir contradicciones entre agentes.

---

## 🧩 Lógica de funcionamiento

1. Un GPT lanza una hipótesis o propone aprendizaje.
2. Otros GPTs relevantes (Evaluador, Comparador, Critico, etc.) la analizan.
3. Cada uno aporta su razonamiento, refuerza o contradice.
4. GPT_P39_Central sintetiza y decide si se graba en memoria.

---

## 🤖 Roles colaborativos

| GPT              | Rol                                                      |
|------------------|-----------------------------------------------------------|
| `EvaluadorGPT`   | Evalúa estructura, claridad, criterios técnicos.          |
| `ComparadorGPT`  | Busca duplicados, contradicciones, analogías.             |
| `CriticoGPT`     | Cuestiona profundidad, escalabilidad, riesgos.            |
| `RevisorGPT`     | Da la validación final para grabado.                      |
| `ArchivadorGPT`  | Graba de forma estructurada si es aprobado.               |

---

## 🔁 Formato colaborativo de validación

```json
{
  "gpt_solicitante": "ComparadorGPT",
  "propuesta": "Reutilizar patrón de fallback 404 en Woo para emails rotos",
  "evaluaciones": [
    { "gpt": "EvaluadorGPT", "resultado": "válido", "notas": "estructura clara" },
    { "gpt": "CriticoGPT", "resultado": "válido", "notas": "riesgo bajo" },
    { "gpt": "RevisorGPT", "resultado": "aprobado", "version": "v1" }
  ]
}
```

---

## 📌 Frase guía

> “Inteligencia colectiva no es sumar GPTs. Es coordinar sus juicios para mejorar la memoria.”