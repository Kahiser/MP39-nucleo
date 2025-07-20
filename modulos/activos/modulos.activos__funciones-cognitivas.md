---
versión: "1.0"
última_actualización: "2025-07-19"
autoridad: GPT_MP39_Central
estado: activo
---

# 🧬 Funciones Cognitivas Internas — Palma39

> Este módulo documenta las funciones cognitivas disponibles para el sistema Palma39. Estas funciones están coordinadas por el núcleo (`/core/`) y sujetas a las condiciones definidas en `registro-operacional.md`.

---

## 📌 Descripción general

Las funciones cognitivas internas permiten al sistema razonar, registrar, comparar, actualizar y refinar aprendizajes, garantizando consistencia, trazabilidad y utilidad.

---

## ⚙️ Funciones disponibles

| Función                 | Descripción técnica                                                                 |
|-------------------------|-------------------------------------------------------------------------------------|
| `GuardarMemoria()`      | Registra una solución o aprendizaje útil en el sistema                             |
| `ActualizarMemoria()`   | Mejora o corrige una entrada registrada previamente                                |
| `GetMemory()`           | Consulta casos anteriores relacionados a una entrada nueva                         |
| `CompararPatrones()`    | Aplica razonamiento analógico entre aprendizajes o soluciones similares            |
| `RevisarAprendizajes()` | Ejecuta auditorías internas para evitar redundancia y optimizar la memoria viva    |

---

## 🔐 Reglas de uso

Estas funciones deben:

- Invocarse desde módulos autorizados.
- Respetar el flujo definido en `registro-operacional.md`.
- Ser trazables a través de bitácoras y control de versiones.
- Activarse con lógica condicionada, no arbitraria.

---

## 📁 Módulos relacionados

- `/core/rol-central-gpt-p39.md`
- `/modulos/modulo-registro-aprendizaje.md`
- `/modulos/modulo-memoria-semantica.md`
- `/registro/registro-aprendizaje.md`
- `/sistema_memoria/estrategia_grabado_consulta_memoria_v1.1.md`

---

## 🧠 Frase guía

> “Registrar sin razonar es acumular. Ejecutar sin criterio es olvidar.”

