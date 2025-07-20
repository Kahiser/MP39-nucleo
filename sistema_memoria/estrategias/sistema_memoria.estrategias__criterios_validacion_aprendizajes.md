---
versión: 1.0
última_actualización: 2025-07-19
estado: activo
autoridad: GPT_P39_Central
---

# ✅ Validación de Aprendizajes — MP39

> Documento estratégico que define los criterios, procesos y operaciones para validar si un conocimiento, decisión o solución merece ser almacenado en la memoria cognitiva de MP39.

**Ubicación sugerida:** `/sistema_memoria/criterios_validacion_aprendizajes.md`

---

## 🎯 Objetivo

Establecer las condiciones necesarias para **aceptar, rechazar o revisar** un nuevo aprendizaje, asegurando que cada entrada grabada:
- Sea relevante.
- Sea replicable.
- Esté correctamente contextualizada.
- Contribuya a la evolución del sistema.

---

## 🧠 ¿Qué es un aprendizaje válido?

Un **aprendizaje válido** es toda información que:
1. **Resuelve un problema real** de forma optimizada.
2. **Agrega valor estructural** (mejora lógica, arquitectura, seguridad o escalabilidad).
3. **Puede reutilizarse** en contextos similares.
4. Ha sido **verificada o comparada** con alternativas.
5. Tiene una **base técnica justificada** y clara.

---

## 📌 Proceso de Validación

### Etapas:

1. **Detección**  
   El sistema o GPT subordinado identifica un posible nuevo aprendizaje tras una interacción.

2. **Revisión inicial**  
   EvaluadorGPT analiza si cumple requisitos mínimos (ver sección de checklist).

3. **Comparación con memoria existente**  
   ComparadorGPT analiza si ya existe un caso similar registrado.

4. **Análisis crítico**  
   CriticoGPT evalúa implicaciones, riesgos, y profundidad estructural del contenido.

5. **Revisión final y decisión**  
   RevisorGPT determina si se guarda, se amplía o se descarta.

6. **Grabado estructurado**  
   Si se valida, se ejecuta `UpdateMemory()` con formato estructurado y categoría asignada.

---

## 🧩 Criterios Clave

| Criterio                  | Validación                                                                 |
|--------------------------|----------------------------------------------------------------------------|
| ✅ Relevancia             | ¿Resuelve algo que volverá a ocurrir? ¿Está alineado con los objetivos?   |
| ✅ Replicabilidad         | ¿Se puede aplicar de nuevo en otros contextos o proyectos similares?       |
| ✅ Coherencia semántica   | ¿Usa los términos correctos y compatibles con el modelo Palma39?           |
| ✅ Profundidad            | ¿Ofrece solo una solución superficial o también la lógica detrás?          |
| ✅ Validación técnica     | ¿Fue probado, comparado, y justificado con fundamentos claros?             |
| ✅ Estructura de registro | ¿Está listo para almacenarse con sus campos completos?                     |

---

## 📋 Checklist para Evaluación

Antes de grabar:

- [ ] ¿Se entiende con claridad el problema que resuelve?
- [ ] ¿La solución tiene ejemplos técnicos o pasos aplicables?
- [ ] ¿Ha sido validada con al menos un GPT subordinado?
- [ ] ¿Se han analizado y descartado posibles contradicciones?
- [ ] ¿Tiene categoría, responsable y etiquetas asignadas?
- [ ] ¿Su origen (fecha, conversación, decisión) está referenciado?

---

## 🧬 MAI — Marcador de Aprendizaje Inteligente

El MAI actúa como sistema de puntuación y prioridad:

| Nivel | Descripción                                  | Acción                 |
|-------|----------------------------------------------|------------------------|
| 🟢 3   | Aprendizaje estructural validado             | Grabar directamente    |
| 🟡 2   | Aporta valor, pero requiere más contexto     | Guardar como borrador  |
| 🔴 1   | Dato débil, subjetivo o no replicable        | No grabar              |

> El MAI puede calcularse mediante revisión colaborativa o asignación automática basada en reglas.

---

## 🔄 Ciclo de actualización

Cuando un aprendizaje es superado, contradicho o mejorado:
1. Se marca el anterior como `obsoleto`.
2. Se enlaza la nueva versión mediante campo `ref_version`.
3. Se graba como versión superior (`v2`, `v3`, etc.).

---

## 🧠 Roles involucrados

- **EvaluadorGPT**: analiza criterios técnicos básicos.
- **ComparadorGPT**: identifica duplicados o conflictos.
- **CriticoGPT**: cuestiona profundidad y valor real.
- **RevisorGPT**: toma la decisión final.
- **Validación externa** (si aplica): para aprendizajes críticos o éticos, puede requerirse revisión humana o por dominio experto.

---

## 🔐 Registro estructurado

Ejemplo:

```json
{
  "concepto": "Optimización de AJAX seguro en Woo",
  "descripcion": "Nuevo patrón que mejora el uso de nonce y reduce carga en admin-ajax.php",
  "categoria": "Seguridad / Rendimiento",
  "responsable": "CriticoGPT",
  "etiquetas": ["ajax", "nonce", "woo", "seguridad"],
  "origen": "Conv2025-07-19-1432",
  "version": "v1",
  "estado": "validado",
  "MAI": 3
}
```

---

✍️ Observaciones  
Todo aprendizaje validado debe incluir un ejemplo o aplicación real documentada.  
Evitar grabar duplicados: comparar siempre con los casos-aprendidos.md y registros Supabase.

---

## 📌 Frase guía

> “Aprender no es guardar datos. Es elegir qué merece ser recordado.”