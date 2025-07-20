---
versión: 1.1
última_actualización: 2025-07-19
estado: activo
autoridad: GPT_P39_Central
---

# 🧠 Estrategia Avanzada de Grabado y Consulta de Memoria GPT P39 (v1.1)

Este documento define las buenas prácticas, optimizaciones técnicas y lógica funcional para el correcto grabado y recuperación de entradas en el sistema de memoria viva de Palma39.

📎 Véase también: [`memoria-viva-ext.v2-adaptado.md`](../memoria-viva-ext.v2-adaptado.md) como documento base simbólico y semántico.

---

## 🧪 Ejemplo de Entrada Mínima Válida

```json
{
  "Concepto": "Error en filtrado de stock Woo",
  "Fecha": "2025-07-19T10:00:00Z",
  "Solucion": "Modificar hook 'woocommerce_product_query'",
  "Prioridad": "Alta",
  "MAI": 7,
  "Etiquetas": ["stock", "woocommerce"]
}
```

---

## I. Validación Previa al Grabado

- Verificar que `Concepto`, `Solución` y `ResumenNarrativo` no estén vacíos ni sean redundantes.
- Asegurar al menos una `Etiqueta` válida.
- `NivelDeConfianza` debe ser coherente con la calidad del contenido.
- Validación por `EvaluadorGPT` opcional.

---

## II. Auto-completado Inteligente

GPT_P39_Central puede completar automáticamente:
- `AplicacionFutura`
- `TipoDeRazonamiento`
- `ModeloCausal`
- `Criticidad`

Esto reduce la carga cognitiva del usuario o agente subordinado.

---

## III. Control de Duplicación Semántica

Usar `hash_semantico = sha256(Concepto + Fecha + Solución)` para prevenir duplicados.

(Alternativa: comparar embeddings antes de insertar.)

---

## IV. Indice de Analogía

- Calcular al grabar la similitud con memorias existentes (0.0 a 1.0).
- Insertar en campo `IndiceAnalogia`.

---

## V. Indexación SQL Recomendada

```sql
CREATE INDEX idx_maia ON MemoriaGPT (MAI);
CREATE INDEX idx_revision ON MemoriaGPT (RevisionSemanal);
CREATE INDEX idx_tipo_razonamiento ON MemoriaGPT (TipoDeRazonamiento);
CREATE INDEX idx_fecha ON MemoriaGPT (Fecha);
CREATE INDEX idx_etiquetas ON MemoriaGPT USING GIN (Etiquetas);
```

---

## VI. Consulta Avanzada por GPTs

### Funciones sugeridas:

```python
ConsultarPorTipo("corrección")
ConsultarCasosRelacionados("hooks de pago")
ConsultarPorAnalogía("errores en checkout")
```

### Endpoint sugerido:

`GET /memorias/pendientes-aprendizaje`

**Criterios:**
- `RevisionSemanal = TRUE`
- `MAI < 6`
- `Criticidad IN ('Alta', 'Ética')`

---

## VII. Ampliaciones Futuras

| Elemento                       | Propósito                                         |
|-------------------------------|--------------------------------------------------|
| Embeddings por entrada        | Búsqueda semántica avanzada                     |
| HistorialMemoriaGPT           | Versionado completo por entrada                 |
| GPT_Auditor                   | Revisión autónoma semanal o mensual             |
| Etiquetas Jerárquicas (`/`)   | Navegación por árbol temático (`/bug/checkout`) |

---

## 🔗 Enlace técnico con Supabase

Para conocer la estructura real de almacenamiento en Supabase, consulta el archivo:  
[`sincronizacion_memoria.sql.md`](/infraestructura/sincronizacion_memoria.sql.md)

---

📁 Ubicación sugerida: `/sistema_memoria/estrategias/estrategia_grabado_consulta_memoria.md`
