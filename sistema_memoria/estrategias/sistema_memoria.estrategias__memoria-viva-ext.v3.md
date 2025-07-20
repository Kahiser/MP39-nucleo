---
versión: 3.0
última_actualización: 2025-07-19
estado: activo
autoridad: GPT_P39_Central
---

# 📘 Sistema de Memoria Viva GPT P39 — Versión Adaptada a BD v2

Este documento describe el funcionamiento operativo del sistema de memoria viva y sus módulos, **actualizados a la versión actual de la base de datos `MemoriaGPT`**, según la estructura definida en Supabase.

---

## 🔹 I. Módulo SPRA (Sistema de Prioridad Razonada Automática)

**Propósito:** Asignar prioridad automática a las entradas según urgencia, criticidad y aplicabilidad.

**Vinculación con la BD:**
- Se refleja en el campo `Prioridad` (`Alta`, `Media`, `Baja`).
- Toma en cuenta:
  - `Criticidad`
  - `MAI`
  - `NivelDeConfianza`

---

## 🔄 II. Revisión Semanal Predictiva

**Propósito:** Detectar entradas que requieren actualización, seguimiento o refuerzo.

**Automatización:**
- Marca el campo `RevisionSemanal = TRUE`
- Se consulta cada 7 días:
  - Entradas con `MAI < 6`
  - Entradas con `Criticidad IN ('Alta', 'Ética')`

---

## 🧠 III. MAI (Marcador de Aprendizaje Interno)

**Propósito:** Calificar el valor cognitivo de una entrada.

**Vinculado a:**
- Campo `MAI` (0 a 10)
- Evaluado al momento del grabado por GPTs evaluadores
- Justificado mediante `ResumenNarrativo` y `LeccionesClaves`

---

## 🧪 IV. SAS (Sistema de Autocrítica Semestral)

**Propósito:** Auditar de forma sistémica las memorias históricas y detectar puntos de obsolescencia o mejora.

**Proceso:**
- Cada 6 meses, `GPT_Auditor` revisa entradas marcadas como `Criticidad = Ética` o `EstadoActual = En revisión`.
- Puede generar nuevas entradas con `Categoria = Autoevaluación` y vincularlas con `CasosRelacionados`.

---

## 🧩 Conexiones con Campos SQL Nuevos

| Campo BD             | Usado por módulo     | Descripción                                |
|----------------------|----------------------|--------------------------------------------|
| `IndiceAnalogia`     | MAI / SPRA           | Indica fuerza de conexión con casos previos |
| `ModeloCausal`       | MAI / SAS            | Describe el tipo de relación causa-efecto  |
| `TipoDeRazonamiento` | SPRA / MAI           | Define si es inductivo, abductivo, etc.    |
| `VersionN`           | SAS                  | Versión cognitiva del registro             |
| `IntuicionGPT`       | MAI                  | Observación complementaria del agente      |

---

## 🧠 Evaluación por GPTs Subordinados

Cada entrada se puede enriquecer o archivar según lo determinen:

- `EvaluadorGPT` → Valida MAI y NivelDeConfianza
- `ArchivadorGPT` → Obsolescencia + Etiqueta de archivo
- `AprendizGPT` → Relee y transfiere aprendizajes con prioridad

---

## 📍 Ejemplo Simplificado de Entrada

```json
{
  "Concepto": "Corrección en validación de email en checkout",
  "Fecha": "2025-07-19T11:00:00Z",
  "Categoria": "Corrección",
  "Solucion": "Uso de regex mejorado en validador JS",
  "AplicacionFutura": "Reusable en cualquier validación de campo Woo",
  "Prioridad": "Alta",
  "EstadoActual": "Vigente",
  "RevisionSemanal": true,
  "MAI": 8.2,
  "NivelDeConfianza": 0.92,
  "Criticidad": "Normal",
  "TipoDeRazonamiento": "Inductivo",
  "ModeloCausal": "Input defectuoso → Validación fallida → Checkout bloqueado",
  "LeccionesClaves": ["Validar siempre formato y contenido", "No confiar en validador del navegador"],
  "CasosRelacionados": [102, 231],
  "Etiquetas": ["checkout", "validación", "WooCommerce", "frontend"]
}
```

---

Fin del documento.