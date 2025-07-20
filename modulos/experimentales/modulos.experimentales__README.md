# 🧪 Módulos Experimentales

Esta carpeta contiene scripts, funciones y módulos en desarrollo. No están validados para entornos de producción, pero forman parte del ciclo de innovación cognitiva de Palma39.

---

## 📄 Archivos incluidos

| Script                         | Descripción breve                                 | Estado       |
|-------------------------------|---------------------------------------------------|--------------|
| autocomparador_semantico_v2.py| Prototipo de analogía semántica entre entradas    | experimental |
| analizador_multiprompt_maia.py| Analiza decisiones entre múltiples GPTs           | experimental |

---

## 🚦 Criterios para salir de experimental

- Integración con PROM activo
- Validación funcional cruzada con memoria
- Revisión por `EvaluadorGPT` o `AuditorGPT`
- Inclusión en pruebas de producción controladas

---

## 🧭 Relación con sistema principal

- `autocomparador_semantico_v2.py` está vinculado con `/prompts/comparador-gpt.md`
- `analizador_multiprompt_maia.py` complementa procesos de `EvaluadorGPT`

---

> ⚠️ No utilizar estos módulos como fuentes de decisión automática sin revisión humana o validación por GPT_P39_Central.