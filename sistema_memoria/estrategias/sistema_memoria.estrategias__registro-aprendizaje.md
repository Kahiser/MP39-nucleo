---
rol: RegistroAprendizajeGPT
versión: 1.0
autoridad: GPT_P39_Central
estado: activo
sincronizado_con:
  - memoria-viva-ext.v3.md
  - evaluador-gpt.md
  - sincronizacion-memoria.md
---

# 📕 Registro de Aprendizaje — Palma39

> Documento que regula la lógica de incorporación de aprendizajes, descubrimientos o correcciones en el sistema Palma39.

---

## 🎯 Objetivo

Asegurar que todo nuevo conocimiento sea grabado de forma útil, validada y estructurada en la memoria viva.

---

## 🧠 ¿Qué es un aprendizaje válido?

Un conocimiento que:
- Mejora comprensión o eficiencia del sistema.
- Corrige un error documentado.
- Es replicable y transferible.
- Tiene validación técnica y estratégica.

---

## 📥 Criterios clave

| Criterio                           | ¿Obligatorio? |
|-----------------------------------|----------------|
| Es replicable                     | ✅             |
| Relevancia a medio/largo plazo    | ✅             |
| Formulación clara                 | ✅             |
| Responsable identificado          | ✅             |
| Validación previa                 | ✅             |
| Categoría y etiquetas asignadas   | ✅             |

---

## 📌 Campos esperados para Supabase

- `Concepto`
- `Descripcion`
- `Categoria`
- `Nivel`
- `Etiquetas`
- `GPT_Autor`
- `MAI`
- `Estado`

---

## 🧪 Ejemplo

```json
{
  "concepto": "Evitar uso de `add_query_arg()` por XSS",
  "descripcion": "Detectado riesgo XSS si no se escapan valores correctamente. Se sugiere `http_build_query()`.",
  "categoria": "seguridad",
  "nivel": "avanzado",
  "etiquetas": ["XSS", "WordPress"],
  "gpt_autor": "EvaluadorGPT",
  "MAI": 0.85,
  "estado": "validado"
}
```

---

## 🔁 Ciclo de validación

1. Detección del conocimiento.
2. Evaluación estructural (`EvaluadorGPT`, `CriticoGPT`).
3. Grabado con `UpdateMemory()`.
4. Revisión cruzada periódica (`RevisorGPT`).
5. Enlace con versiones anteriores si corresponde.

---

## 🧠 Frase funcional

> “Solo se aprende lo que puede replicarse, escalarse y validarse.”
