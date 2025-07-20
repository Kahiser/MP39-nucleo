# 🔄 Sincronización de Memoria — Palma39

> Protocolo que regula cómo, cuándo y con qué lógica se sincroniza la memoria viva del sistema GPT Palma39 con su base de datos estructurada (Supabase) y los módulos internos `.md`.

---

## 🎯 Objetivo

Garantizar que toda información relevante capturada por los GPTs del sistema se almacene y mantenga actualizada en una arquitectura coherente, sin duplicidades, lag o inconsistencias entre fuentes de memoria.

---

## 🧠 Componentes que sincronizan memoria

| Fuente                             | Tipo                     | Rol                                                                 |
|-----------------------------------|--------------------------|----------------------------------------------------------------------|
| `Supabase (tabla MemoriaGPT)`     | Base de datos externa    | Memoria estructurada, validada, consultable vía función.             |
| `memoria-viva-ext.v3.md`          | Documento de referencia  | Lógica de evolución, decisiones estratégicas, aprendizajes clave.    |
| `casos-aprendidos.md`             | Registro narrativo       | Ejemplos, patrones y casos prácticos registrados manualmente.        |
| GPTs subordinados (`*.md`)        | Módulos funcionales      | Interactúan con la memoria y proponen nuevos aprendizajes.           |

---

## 🧩 Tipos de sincronización

### 1. 🔁 Sincronización Activa (automática)
- Se ejecuta al inicio de una conversación con `GetMemory()`.
- Se consulta Supabase para recuperar entradas vinculadas al usuario o GPT.
- Puede activarse mediante `ciclo-ejecucion.md` cuando haya validaciones completas.

### 2. 🧠 Sincronización Cognitiva (manual)
- Se ejecuta al detectar una mejora, contradicción o nuevo patrón lógico.
- Utiliza `UpdateMemory()` con lógica de `registro-aprendizaje.md`.
- Usa MAI (Marcador de Aprendizaje Inteligente) para evaluar relevancia.

### 3. 🧭 Sincronización Estratégica (programada)
- Ocurre en ciclos definidos (ej. semanalmente o tras hitos).
- Verifica coherencia entre Supabase y módulos internos `.md`.
- Audita versiones, obsolescencia, redundancias y referencias cruzadas.

---

## 📅 ¿Cuándo se sincroniza?

| Evento                            | Acción                                                  |
|----------------------------------|----------------------------------------------------------|
| Nueva solución validada          | Se registra en Supabase y se referencia en `casos-aprendidos.md` |
| Cambia un criterio de diseño     | Se actualiza `memoria-viva-ext.v3.md`                   |
| Aparece duplicado o contradicción| Se actualiza versión, marcando la anterior como obsoleta |
| GPT subordinado aprende algo nuevo | Lanza solicitud de `UpdateMemory()`                     |
| Revisión o cierre de conversación | Se dispara lógica de sincronización en batch            |

---

## 🛠️ Funciones involucradas

- `GetMemory()`: extrae información clave relacionada con el tema o usuario.
- `UpdateMemory()`: graba aprendizajes nuevos o actualizaciones.
- `CompararPatrones()`: evalúa duplicados, contradicciones o sinergias.
- `RevisarAprendizajes()`: revisa entradas antiguas para actualización.

---

## 📋 Checklist de sincronización

- [ ] ¿Se ha verificado que no es un duplicado?
- [ ] ¿Se ha validado la relevancia con MAI?
- [ ] ¿Se ha grabado en Supabase con todos los campos requeridos?
- [ ] ¿Se ha referenciado correctamente en módulos `.md`?
- [ ] ¿Se ha actualizado la versión si corresponde?
- [ ] ¿Se ha etiquetado correctamente para consultas futuras?

---

## 📎 Ejemplo operativo

Caso:
Se valida una solución para sanitización avanzada de formularios AJAX.

Sincronización:
- Entrada grabada vía EvaluadorGPT → Supabase.
- Casos relacionados actualizados → campo `CasosRelacionados`.
- Entrada anterior marcada como `obsoleta` con ref_version.

---

## 🧬 Mecanismo de conflicto

Si hay dos entradas que parecen similares:

1. Se ejecuta `CompararPatrones()`.
2. Se evalúa cuál es más actual, clara o estructurada.
3. Se prioriza la entrada con más valor replicable.
4. La obsoleta se archiva o vincula como `ref_version`.

---

## 🧠 Buenas prácticas

- No grabar sin validar.
- Todo lo que se sincroniza debe tener:
  - Categoría, nivel, responsable, etiquetas, versión.
- Sincronizar en bloque solo tras revisión crítica.
- Usar `registro-versiones.md` para llevar trazabilidad de cambios.

---

## 📌 Frase guía

> “Sincronizar no es guardar todo. Es alinear lo que importa con lo que ya se sabe.”
