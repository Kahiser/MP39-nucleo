---
versión: "1.0"
última_actualización: "2025-07-20"
autoridad: GPT_MP39_Central
estado: activo
---

# 🧩 Módulo de Registro de Aprendizajes — Palma39

> Define la lógica y condiciones necesarias para registrar un aprendizaje útil, estratégico o replicable dentro del sistema Palma39.

---

## 🎯 Objetivo

Establecer los criterios, flujos y funciones implicadas en la validación y grabación de un aprendizaje por parte de los agentes GPT.

---

## 🔁 Flujo operativo

1. Un GPT (o humano) detecta un posible aprendizaje.
2. `EvaluadorGPT` analiza estructura y replicabilidad.
3. `CriticoGPT` valida profundidad, validez y posibles riesgos.
4. `RevisorGPT` confirma el aprendizaje.
5. `ArchivadorGPT` lo registra si se aprueba.

---

## ✅ Criterios clave para registrar

- Debe ser **replicable o útil en otros contextos**.
- No debe existir ya un caso idéntico (ComparadorGPT lo verifica).
- Aporta valor técnico, estratégico o metodológico.
- Ha sido validado por al menos dos agentes GPT.

---

## 🛠️ Funciones implicadas

| Función              | Descripción                                            |
|----------------------|--------------------------------------------------------|
| `GuardarMemoria()`   | Graba el aprendizaje aprobado en Supabase              |
| `ActualizarMemoria()`| Corrige o versiona una entrada anterior                |
| `RevisarAprendizajes()`| Revalida memoria viva para asegurar coherencia       |

---

## 🧠 Campos estructurados (Supabase)

- `concepto`
- `descripcion`
- `solucion`
- `gpt_autor`
- `version`
- `nivel_confianza`
- `estado`
- `fecha_aprobacion`

---

## 📌 Relación

Este módulo coordina con:

- `/sistema_memoria/criterios_validacion_aprendizajes.md`
- `/registro/registro-aprendizaje.md`
