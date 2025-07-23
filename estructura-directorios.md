🔖 Versión: 1.1 — Actualizado: 2025-07-20

# 🧱 Estructura de Directorios — Repositorio MP39 Núcleo

Este documento detalla la función y relación de cada carpeta principal del repositorio `MP39-nucleo`, dentro del sistema cognitivo Palma39.

---

## 📁 `/prompts/`
Contiene los archivos `.md` con los prompts individuales de cada GPT subordinado (EvaluadorGPT, RevisorGPT, AuditorGPT, etc.).  
Función: Modularidad de roles GPT — cada archivo representa su identidad, comportamiento y parámetros cognitivos.

---

## 📁 `/modulos/`
Módulos activos de funciones cognitivas (memoria, razonamiento, sincronización).  
Función: Define lógica activa que ejecuta el núcleo GPT central.

---

## 📁 `/memoria/`
Archivos que representan memoria viva estructurada (`memoria-viva-ext.v3.md`, `registro-operacional.md`, etc.).  
Función: Contener aprendizajes validados, patrones y evolución del sistema.

---

## 📁 `/sistema/`
Scripts, configuraciones y documentación técnica para sincronización Supabase, autenticaciones y automatismos.  
Función: Infraestructura técnica del sistema Palma39.

---

## 📁 `/documentos/`
Documentos estratégicos, éticos, metodológicos y de diseño base.  
Función: Soporte teórico y fundacional del sistema cognitivo.

---

## 📁 `/recursos/`
Materiales complementarios de referencia externa: documentación de herramientas, reproductores clave (ej. Sonaar), enlaces útiles y manuales.  
Función: Expandir el conocimiento del sistema hacia herramientas de terceros relevantes para la operación y desarrollo del proyecto Palma39.

---

## 📄 `index.md`
Este archivo. Mapa general de navegación y conexión semántica del repositorio.

## 📄 `README.md`
Documento inicial de presentación y contexto general del repositorio.

---

## 🧭 Observaciones
- Todas las carpetas están diseñadas para escalar progresivamente con el sistema.
- Se recomienda mantener esta estructura modular para claridad, mantenibilidad y sincronización con Supabase y GPTs subordinados.
