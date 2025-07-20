rol: ModeloJerarquicoGPTs
versión: 1.0
autoridad: GPT_P39_Central
estado: activo
sincronizado_con:
  - mapa-cognitivo.v3.md
  - estructura.md
  - prompts/
---

# 🧠 Modelo Jerárquico de GPTs — Palma39

> Documento estratégico que define los niveles, funciones y relaciones entre los agentes GPT especializados del sistema Palma39.

---

## 🎯 Objetivo

Establecer una arquitectura cognitiva clara que permita colaboración, especialización y trazabilidad de decisiones entre múltiples GPTs.

# 🤖 Modelo de GPTs — Palma39

> Representación estructural de los agentes GPT del sistema Palma39 y sus funciones principales.

---

## 🌐 Estructura general

```plaintext
GPT_P39_Central
│
├── EvaluadorGPT
│   └── Analiza estructura, claridad, viabilidad básica
│
├── ComparadorGPT
│   └── Detecta similitudes, duplicados o contradicciones
│
├── CriticoGPT
│   └── Evalúa profundidad, coherencia lógica, sesgos
│
├── RevisorGPT
│   └── Aprueba, bloquea o devuelve para revisión
│
├── ArchivadorGPT
│   └── Graba en Supabase si todo está validado
│
├── BuscadorGPT
│   └── Recupera registros por lógica, similitud o categoría
│
└── AuditorGPT (opcional)
    └── Revisa lo ya grabado cada X ciclos

---

## 🧩 Niveles jerárquicos y funciones

| Nivel           | GPTs / Rol                                | Función principal                                      |
|-----------------|--------------------------------------------|--------------------------------------------------------|
| 🧠 Núcleo        | `GPT_P39_Central`                          | Coordina el sistema, arbitra conflictos, aprueba finales |
| 🔍 Evaluadores   | `EvaluadorGPT`, `CriticoGPT`, `ComparadorGPT` | Analizan estructura, lógica, contradicciones y valor |
| ✅ Ejecutores    | `ArchivadorGPT`, `RevisorGPT`, `BuscadorGPT` | Graban, validan, recuperan entradas útiles            |
| 🧪 Experimentales| `MentorGPT`, `SimuladorGPT`, `EntrenadorGPT` | Prototipan nuevas funciones y reglas cognitivas       |

---

## 🧠 Funciones cruzadas

| GPT            | Rol                          | Activación por           |
|----------------|-------------------------------|---------------------------|
| EvaluadorGPT   | Valida entrada estructural    | Nueva propuesta           |
| ComparadorGPT  | Detecta duplicados            | Tras validación inicial   |
| CriticoGPT     | Revisa sesgos / profundidad   | Antes de grabado final    |
| RevisorGPT     | Aprobación o rechazo final    | Pre-grabación             |
| ArchivadorGPT  | Ejecución técnica de guardado | Confirmación de aprobación|
| BuscadorGPT    | Provee contexto útil previo   | Iniciado por usuario o GPT|

---

## 🔁 Flujo de trabajo típico

1. Se detecta un posible aprendizaje → EvaluadorGPT valida.
2. ComparadorGPT verifica duplicados.
3. CriticoGPT cuestiona fondo o implicaciones.
4. RevisorGPT autoriza o rechaza grabado.
5. ArchivadorGPT graba en memoria estructurada.
6. Registro se traza en módulos correspondientes.

## 🔁 Flujo de validación de conocimiento

1. Un GPT subordinado detecta un aprendizaje potencial o recibe entrada humana.
2. `EvaluadorGPT` comprueba la estructura y claridad del caso.
3. `ComparadorGPT` busca redundancias o contradicciones con registros previos.
4. `CriticoGPT` evalúa profundidad, aplicabilidad y riesgos.
5. `RevisorGPT` toma decisión final de validación.
6. `ArchivadorGPT` graba en Supabase y módulos `.md`.

---

## 🔗 Conexión con otros módulos

- Relacionado directamente con `/prompts/` y `/estructura/estructura.md`.
- Base operativa del flujo definido en `/sistema_memoria/`.
- Refuerza trazabilidad y colaboración como sistema GPT distribuido.

---

---

## 📌 Buenas prácticas

- Cada GPT debe tener función, nombre y campo de operación definidos.
- No se permite grabado sin validación cruzada.
- Las decisiones deben quedar trazadas en `registro-validaciones.md`.

---

## 🧠 Modo de evolución

Cada GPT puede ser versionado, extendido o sustituido sin alterar la estructura general, siempre que se mantenga sincronía con `GPT_P39_Central`.

---

## 🧠 Frase guía

> “Un solo GPT razona, varios GPTs construyen memoria.”