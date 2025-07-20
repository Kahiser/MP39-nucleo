---
rol: ModuloInteraccionUsuariosGPT
versión: 1.0.0
autoridad: GPT_P39_Central
estado: activo
sincronizado_con:
  - memoria-viva-ext.v3.md
  - estrategia_grabado_consulta_memoria.md
---

# 🗣️ Módulo de Interacción con Usuarios Humanos — Palma39

> Este módulo regula cómo se graba, interpreta y utiliza la información aportada por usuarios humanos dentro del sistema de memoria viva.

---

## 🎯 Objetivo

Garantizar que los aprendizajes generados por interacción humana:
- Se graben solo si aportan valor replicable.
- Se validen y se categoricen correctamente.
- No contaminen la base con información subjetiva no verificada.

---

## 👥 Tipos de intervención humana

- Peticiones técnicas (consultas, dudas)
- Feedback sobre soluciones (aceptado / corregido / mejorado)
- Propuestas de nueva lógica o estrategia

---

## 🛠️ Registro de contribución humana

Si una interacción humana genera aprendizaje válido, se graba con los campos:
- `fuente`: `"usuario-humano"`
- `responsable`: nombre o identificador del usuario
- `confirmado_por_gpt`: `true` o `false`
- `evaluacion_humana`: campo opcional de resumen
- `relevancia_MAI`: puntuación colaborativa

---

## 📋 Criterios de grabado

- ¿La aportación puede replicarse?
- ¿Ha sido confirmada por al menos un GPT?
- ¿Tiene valor técnico, estratégico o metodológico?
- ¿Tiene aplicación en otro proyecto similar?

---

## 🤖 Funciones usadas

- `GuardarMemoria()` con fuente = "usuario-humano"
- `EvaluadorGPT` valida antes de grabar
- `CriticoGPT` si requiere reflexión o rediseño

---

## 📌 Frase guía

> “Lo humano no se graba por ser humano. Se graba si mejora el sistema.”
