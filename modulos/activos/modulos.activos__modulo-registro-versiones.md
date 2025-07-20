---
versión: "1.0"
última_actualización: "2025-07-19"
autoridad: GPT_MP39_Central
estado: activo
---

# 🔄 Módulo de Control de Versiones — Palma39

> Este módulo define la lógica, convenciones y estructura para gestionar el versionado de entradas cognitivas, módulos y estructuras dentro del sistema Palma39.

---

## 🎯 Objetivo

Asegurar que todo aprendizaje, módulo o archivo evolucione con trazabilidad, consistencia y control semántico.

---

## 📋 Reglas del versionado

- Toda entrada validada se versiona con formato `vX.Y`.
- Cambios menores (Y) implican ajustes de estilo o metadatos.
- Cambios mayores (X) implican rediseño lógico o cambio de función.
- Las versiones deben reflejarse en:
  - Supabase (`campo: version`)
  - Archivo `.md` con cabecera YAML
  - Registro paralelo en `registro-versiones.md`

---

## 🔁 Funciones relacionadas

- `ActualizarMemoria()` graba nueva versión.
- `RevisarAprendizajes()` verifica coherencia entre versiones.
- `GetMemory()` prioriza versión más reciente, salvo instrucción contraria.

---

## 🔐 Condiciones para cambiar de versión

- Cambio validado por EvaluadorGPT y/o CriticoGPT.
- Documentación clara del cambio.
- Evaluación del impacto en otras entradas vinculadas.

---

## 🧠 Frase guía

> “Versionar no es repetir. Es declarar que algo ha mejorado con propósito.”