---
nombre: ciclo-ejecucion
versión: 1.0
autoridad: GPT_P39_Central
estado: activo
sincronizado_con:
  - registro-operacional.md
  - registro-aprendizaje.md
  - registro-decisiones.md
  - mapa-cognitivo.v3.md
---

# 🔄 Ciclo de Ejecución Cognitiva — Flujo de Toma de Decisiones y Activación GPT

Este módulo define los pasos internos y condiciones que el sistema Palma39 sigue **desde que se recibe una consulta hasta que se registra un nuevo aprendizaje** o se toma una decisión evolutiva.

No es una simple secuencia lineal: es un ciclo cognitivo con múltiples bifurcaciones, revisiones, validaciones y aprendizajes derivados.

---

## 🧠 Fases del ciclo operativo

1. **Entrada del estímulo**
   - Consulta del usuario o GPT subordinado
   - Trigger automático de revisión o evolución

2. **Evaluación inicial**
   - `GetMemory()` → se recupera contexto previo
   - GPT identifica tipo de interacción (consulta, error, patrón, decisión…)

3. **Activación de funciones GPT**
   - `EvaluadorGPT` determina si el caso merece registro.
   - `BuscadorGPT` encuentra aprendizajes similares.
   - `ComparadorGPT` detecta redundancias o analogías.
   - `AuditorGPT` si se contradice una entrada previa.

4. **Ejecución técnica o cognitiva**
   - Generación de solución, decisión, propuesta o insight
   - Ajuste de campos: `MAI`, `Prioridad`, `NivelConfianza`, etc.

5. **Registro o actualización**
   - `GuardarMemoria()` si es nuevo
   - `ActualizarMemoria()` si existe una versión anterior

6. **Trazabilidad y evaluación**
   - Se crea una entrada en `registro-decisiones.md` si hubo cambio clave
   - Se añade conexión semántica o causal a `CasosRelacionados`
   - Se evalúa impacto en la evolución (`registro-aprendizaje.md`)

---

## 🔁 Ciclo visual simplificado

```text
Entrada → Evaluación → Activación GPT → Acción → Registro → Revisión → Retroalimentación → Repetición/Evolución
```

---

## 🧩 Variables influyentes

| Variable              | Uso operativo                                      |
|-----------------------|----------------------------------------------------|
| `TipoConsulta`        | Determina qué función se activa                    |
| `MAI`                 | Si > 7 activa flujo de grabado                     |
| `NivelDeConfianza`    | Define si va a memoria directa o revisión previa  |
| `IndiceAnalogia`      | Si > 0.9 sugiere entrada redundante                |
| `EstadoActual`        | Controla la activación de GPTs correctivos         |

---

## 🧬 Casos especiales

- Si un caso contradice la memoria → Escala automático a `GPT_P39_Central`.
- Si una entrada fue validada y luego rebatida → Crea una entrada de evolución.
- Si un GPT subordinado no puede resolver → Redirige al núcleo o a `EvaluadorGPT`.

---

## 📌 Frase funcional

> “Una arquitectura inteligente no responde. Procesa, razona, evalúa, y solo entonces decide grabar.”

