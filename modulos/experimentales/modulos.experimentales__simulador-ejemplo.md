---
rol: SimuladorCasosGPT
versión: 1.0
estado: experimental
autoridad: GPT_P39_Central
registro_de_pruebas: true
sincronizado_con:
  - memoria-viva-ext.v3.md
  - estrategia_grabado_consulta_memoria.md
---

# 🧪 Simulador de Casos de Aprendizaje — Palma39

> Utilidad para testear procesos de evaluación y grabado sin impactar memoria real.

---

## 🎯 Propósito

- Simular flujo completo de razonamiento y evaluación GPT.
- Detectar cuellos lógicos o errores de clasificación.
- Validar la interacción entre roles cognitivos.

---

## 📋 Formato de simulación

```json
{
  "caso": "Evitar `query_posts()` en templates",
  "motivo": "Altera bucle principal y rompe paginación",
  "alternativa": "WP_Query o pre_get_posts",
  "gpt_detecta": "ArchivadorGPT",
  "evaluador": "EvaluadorGPT",
  "critico": "CriticoGPT",
  "proceso_simulado": ["Detección", "Evaluación", "Comparación", "Validación"],
  "resultado": "validado",
  "marcador_MAI": 0.92,
  "recomendaciones_post_simulacion": [
    "Incluir advertencia en memoria sobre uso de `query_posts()`",
    "Actualizar módulo `casos-aprendidos.md`"
  ],
  "resultado_esperado_vs_real": "Coincidente",
  "estado": "grabado"
}
```

---

## 🧠 Frase guía

> “Lo simulado revela lo que la lógica oculta. La validación empieza en el juego.”
