---
versión: "1.0"
última_actualización: "2025-07-19"
autoridad: GPT_MP39_Central
estado: activo
---

# 🏗️ Infraestructura Técnica del Sistema — Palma39

Este directorio contiene la documentación técnica relacionada con la implementación estructural y la conexión del sistema Palma39 con bases de datos externas, como Supabase.

---

## 📂 Contenido

| Archivo                          | Descripción                                                   |
|----------------------------------|---------------------------------------------------------------|
| `sincronizacion_memoria.sql.md` | Esquema SQL y definición estructural de la tabla en Supabase |

---

## 📌 Propósito

Asegurar una alineación total entre las operaciones internas de los GPTs del sistema y la estructura de datos en producción. Toda validación estructural se basa en este archivo.

---

## 🧠 Notas

- Las funciones como `GuardarMemoria()` o `ActualizarMemoria()` deben cumplir con esta estructura.
- Los roles `archivador-gpt`, `evaluador-gpt` y `registro-operacional` hacen referencia a esta sincronización.

