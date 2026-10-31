# Lucas F. Meneses — Portafolio de Ingeniería y Casos de Estudio de Arquitectura

> Software Engineer · Applied AI · Full-stack · Argentina

Bienvenido a mi portafolio público de arquitectura e ingeniería. Este repositorio documenta casos de estudio técnicos, patrones de diseño y prácticas de ingeniería desarrolladas en sistemas reales, elaborado bajo una metodología clean-room para equipos técnicos y reclutadores.

---

## Índice del Portafolio

### Casos de Estudio de Arquitectura

| Sistema | Dominio y Alcance | Aspectos Destacados | Caso de Estudio |
| :--- | :--- | :--- | :--- |
| **Quiddit** | Orquestación de IA Multi-Proveedor y Memoria a Largo Plazo | PostgreSQL + pgvector, failover dinámico (Gemini, Together AI, Ollama), defensa contra prompt injection, sanitización local de imágenes con DETR, Docker + Nginx (~60k LOC) | [Leer Caso de Estudio](case-studies/quiddit.es.md) |
| **Qvision** | Captura Edge de Video y Sensores en Tiempo Real | React Native + módulos nativos en Kotlin (IMU cada 100 ms), privacidad on-device (detección facial con TFLite + detección de documentos con ML Kit), admin en Supabase, segmentación YOLO (~55k LOC) | [Leer Caso de Estudio](case-studies/qvision.es.md) |
| **umi** | Visión en el Edge Offline-First y Procesamiento de Documentos | MVP en Flutter, lectura on-device de QR y OCR con Google ML Kit, Supabase con Row-Level Security (RLS) | [Leer Caso de Estudio](case-studies/umi.es.md) |

### Metodologías de Desarrollo

- **[Desarrollo Agéntico Human-in-the-Loop](workflow/agentic-development.es.md)**: Una metodología estructurada para combinar agentes de IA (Claude, Jules/Antigravity, Codex) con disciplina de ingeniería, auditorías de seguridad, barreras de tests automatizados y supervisión humana.

---

## Competencias Técnicas Principales

- **Sistemas de IA Aplicada y ML**: Failover multi-proveedor de LLMs, validación estricta de esquemas JSON, búsqueda semántica con pgvector, modelos de visión en el edge (DETR, YOLO, TFLite, ML Kit).
- **Ingeniería de Seguridad y Privacidad**: Aislamiento multicapa contra prompt injection, validación recursiva de esquemas, redacción local sin fugas (sanitización de personas y documentos antes de salir de la red), Row-Level Security (RLS).
- **Arquitectura Full-Stack y Mobile**: Servicios en Node.js/TypeScript, Flutter, React Native con módulos nativos en Kotlin, interfaces en React/Vite, despliegues contenerizados en Docker con proxies inversos.
- **Metodologías Modernas de Ingeniería**: Flujos agénticos supervisados por humanos, tests como compuerta de merge, integración continua automatizada y separación clara de responsabilidades.

---

## Decisiones de Diseño

1. **Documentación Clean-Room**: Todos los casos de estudio describen arquitecturas, fronteras de interfaz y compromisos operativos a nivel de componentes. No se incluye lógica propietaria, esquemas internos, tokens ni datos de usuarios.
2. **Privacidad Primero en el Edge**: Tanto en visión computacional como en flujos generativos, los datos sensibles y el PII se procesan localmente en el dispositivo de captura antes de cruzar la frontera de red.
3. **Resiliencia Mediante Redundancia Multi-Proveedor**: En lugar de atar flujos críticos a un único proveedor de modelos, el orquestador implementa comprobaciones de salud, circuit breakers y esquemas de contingencia entre proveedores cloud y locales.
4. **Validación Estricta de Esquemas**: Las respuestas desestructuradas de los modelos se tratan como entradas no confiables, pasando por sanitización recursiva y validadores de esquemas JSON antes de modificar el estado del sistema.

---

## Inicio Rápido y Navegación

Para explorar el repositorio y visualizar los diagramas de arquitectura:

```bash
# Clonar el repositorio
git clone https://github.com/lucasfmeneses/qproject-showcase.git
cd qproject-showcase

# Ejecutar la validación de markdown localmente
npm install
npm run lint
```

- Revisá los diagramas de arquitectura en `/case-studies/` (renderizados de forma nativa en GitHub mediante Mermaid).
- Revisá el flujo de ingeniería agéntica en `/workflow/agentic-development.es.md`.
- Inspeccioná los patrones de configuración de entorno en `.env.example`.

---

## Limitaciones

- **Alcance Documental**: Este repositorio funciona como un portafolio de arquitectura técnica y no contiene código fuente propietario, pesos de modelos internos ni credenciales operativas.
- **Nivel de Abstracción**: Los diagramas representan relaciones entre subsistemas y flujos de datos a nivel de cajas, sin exponer detalles de clases internas de implementación.
- **Interfaces de Demostración**: Todo fragmento de código o variable de entorno presentada corresponde a interfaces genéricas diseñadas exclusivamente con fines ilustrativos.

---

## Licencia

Este repositorio se distribuye bajo los términos de la [Licencia MIT](LICENSE).
