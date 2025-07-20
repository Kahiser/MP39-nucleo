---
nombre: registro-operacional
versión: 1.0
autoridad: GPT_P39_Central
estado: activo
sincronizado_con:
  - estrategia_grabado_consulta_memoria.md
  - memoria-viva-ext.v3.md
  - mapa-cognitivo.v3.md
---

# 🧠 Registro Operacional — Ciclo de Activación Cognitiva y Validación

Este módulo define **cuándo, cómo y bajo qué condiciones** se ejecutan funciones como `GuardarMemoria()`, `ActualizarMemoria()`, `RevisarAprendizajes()` o `CompararPatrones()`.

Estandariza las decisiones automáticas y humanas del sistema cognitivo Palma39.

---

## 🎯 Objetivo

Garantizar que:
- Solo se graba conocimiento relevante, estratégico y validado.
- Las decisiones de grabado, consulta o comparación sigan un flujo lógico claro.
- Se minimice la redundancia y se preserve la calidad de la memoria.

---

## 🔁 Flujo operativo general

1. **Inicio de sesión GPT**  
   → `GetMemory()` se ejecuta automáticamente para recuperar casos relacionados.

2. **Ingreso de nuevo aprendizaje**  
   → Se evalúa con `EvaluadorGPT` antes de grabar.

3. **Comparación con casos existentes**  
   → `ComparadorGPT` determina redundancia o analogía.

4. **Grabado definitivo**  
   → Si validado: `GuardarMemoria()` almacena en Supabase.  
   → Si requiere revisión: se mueve a `en revisión`.

5. **Revisión periódica o por conflicto**  
   → `AuditorGPT` activa `RevisarAprendizajes()` según fecha o alerta cognitiva.

---

## ✅ Condiciones para `GuardarMemoria()`

| Criterio                         | Valor mínimo exigido                      |
|----------------------------------|-------------------------------------------|
| MAI                              | ≥ 6                                       |
| Aplicación futura                | Clara, específica, reutilizable           |
| NivelDeConfianza                 | Medio o alto                              |
| EstadoActual                     | `validado` o `nuevo_valido`               |
| Categoría                        | Incluida en ontología activa              |

---

## 🧪 Validaciones antes de registrar memoria

Antes de registrar un aprendizaje en Supabase o memoria viva, se deben cumplir los siguientes chequeos:

- Validación semántica de utilidad y originalidad
- Validación técnica por parte de `evaluador-gpt`
- Validación estructural contra los campos definidos en Supabase  
  → Véase: `/infraestructura/sincronizacion_memoria.sql.md`
  
---
  
## ⚠️ Casos que se mueven a revisión

- Ambigüedad en el contexto
- Falta de aplicabilidad futura
- Contradicciones no resueltas
- Registro con MAI < 5 sin justificación clara

---

## 🔄 Funciones permitidas y su propósito

| Función                    | Descripción                                         |
|----------------------------|-----------------------------------------------------|
| `GuardarMemoria()`         | Almacenar nuevo conocimiento en base Supabase      |
| `ActualizarMemoria()`      | Ajustar campos ya grabados (estado, versión, etc.) |
| `RevisarAprendizajes()`    | Auditoría periódica o puntual                      |
| `CompararPatrones()`       | Detección semántica de analogías o redundancias    |
| `GetMemory()`              | Cargar experiencias pasadas por contexto           |

---

## 📦 Gatillos automáticos

- Cada 12 horas → trigger de revisión (`RevisarAprendizajes()`)
- Si MAI ≥ 9 → grabado directo con supervisión de `EvaluadorGPT`
- Si 3 GPTs subordinados coinciden en validación → se graba sin intervención manual

---

## 📌 Frase funcional

> “Un sistema cognitivo no guarda lo que ve. Guarda lo que razona. Lo que puede transformar futuras decisiones.”

