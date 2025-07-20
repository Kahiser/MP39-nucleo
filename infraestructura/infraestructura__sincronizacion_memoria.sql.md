---
versión: "1.0"
última_actualización: "2025-07-19"
autoridad: GPT_MP39_Central
estado: activo
---

# 📡 Sincronización Técnica con Supabase — `sincronizacion_memoria.sql.md`

Este archivo describe la estructura técnica utilizada para sincronizar los aprendizajes cognitivos registrados por los agentes GPT con la base de datos Supabase, usando SQL como interfaz declarativa.

---

## 🧱 Estructura SQL — Tabla `memoria_gpt`

```sql
CREATE TABLE memoria_gpt (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  concepto TEXT NOT NULL,
  solucion TEXT NOT NULL,
  nivel_confianza TEXT DEFAULT 'medio',
  responsable TEXT,
  estado_actual TEXT DEFAULT 'pendiente',
  casos_relacionados TEXT[],
  mai TEXT,
  fecha_registro TIMESTAMP DEFAULT now(),
  etiquetas TEXT[]
);
```

---

## 🔁 Mecanismo de sincronización

Cada vez que se registra un aprendizaje mediante `GuardarMemoria()`:

1. Se valida la estructura semántica y técnica.
2. Se crea un nuevo `INSERT` con los campos válidos.
3. Se sincroniza vía Supabase REST API o middleware backend.
4. La entrada queda disponible para consulta mediante `GetMemory()` o vía interfaz visual.

---

## 🧩 Integración con agentes

| Agente           | Rol en la sincronización                      |
|------------------|------------------------------------------------|
| `archivador-gpt` | Genera la entrada estructurada                |
| `evaluador-gpt`  | Valida que cumple con la semántica esperada   |
| `revisor-gpt`    | Verifica coherencia antes del guardado final  |

---

## 🧠 Observaciones

- Todos los campos son obligatorios salvo `responsable`, `mai` y `etiquetas`.
- Se recomienda mantener un middleware seguro entre GPT y Supabase para evitar corrupción de datos.
- Esta estructura puede evolucionar en futuras versiones del sistema Palma39.

---

## 🔄 Última sincronización con Supabase:

Archivo actualizado en base al esquema recibido el 19 de julio de 2025.

---

## 🔧 Funciones complementarias sugeridas

Estas funciones no son obligatorias para la sincronización básica, pero pueden integrarse desde otros módulos especializados para enriquecer el ecosistema Palma39:

| Función                       | Descripción                                                                 |
|------------------------------|-----------------------------------------------------------------------------|
| `ValidarEntrada()`           | Comprueba si los campos cumplen formato y lógica antes de insertarse        |
| `RelacionarGPT()`            | Asocia la entrada registrada al GPT responsable de su generación            |
| `ConsultarMemoriaPorTema()`  | Filtra y consulta aprendizajes pasados por categoría o palabra clave        |
| `ActualizarNivelConfianza()` | Recalcula nivel_confianza al recibir nueva información relacionada          |
| `AuditarEntradas()`          | Identifica entradas redundantes, incoherentes o en conflicto                |
| `EtiquetarAutomáticamente()` | Clasifica automáticamente las entradas según patrones semánticos detectados |

> Estas funciones pueden implementarse desde `auditor-gpt.md`, `revisor-gpt.md` u otros módulos del sistema.

