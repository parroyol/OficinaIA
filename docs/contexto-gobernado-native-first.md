# Contexto gobernado y Native-First

**Estado:** síntesis reutilizable de decisiones y evidencias observadas; no sustituye las fuentes de cada proyecto ni convierte prácticas parciales en reglas universales.

## Propósito y alcance

Relacionar tres líneas de trabajo que comparten el uso controlado del contexto y la trazabilidad, manteniendo separado su ámbito. Esta guía consolida referencias y límites; no fusiona código, ramas ni mecanismos de ejecución.

## Capas relacionadas

| Capa | Qué gobierna | Fuente principal | Estado observado |
|---|---|---|---|
| Perfil operativo | Cómo investiga y comunica evidencia un asistente entre tareas de repositorio | [Perfil Operativo](https://github.com/parroyol/OficinaIA/blob/main/docs/perfil-operativo.md) | Publicado en `main`; referencia canónica de esta colección. |
| Context-On-Demand del producto | Cuándo y cómo una tarea del producto recupera evidencia documental | Guía, instrucciones y skill de Context-On-Demand del worktree del producto | Hay artefactos y validación CLI con fixtures sintéticos. La activación automática por Copilot Desktop/Side Chat no quedó acreditada. No se presenta como política global ya desplegada. |
| Trazabilidad operativa | Cómo una actividad puede relacionar alcance, revisión, hallazgos, acciones, ejecución, validación y resultado | `PRACTICA-OPERATIVA-OBSERVADA.md` y expediente del piloto en el worktree de auditoría | Referencia descriptiva; piloto validado con reservas. No se acreditó aprobación institucional ni aplicación universal. |

El gestor de contexto híbrido tratado en otra aplicación es una línea relacionada por tema, pero pertenece a otro proyecto. No se integra aquí como arquitectura o implementación de OficinaAI.

## Decisiones reutilizables

- Mantener distinto el perfil permanente del estado particular de cada conversación.
- Consultar contexto adicional solo si las fuentes ya disponibles no bastan para el objetivo. Preferir recuperación acotada a precargar documentos o historiales.
- Hacer explícitos la fuente, la observación y el estado de verificación; separar hechos, inferencias y brechas.
- En recuperación documental específica de un producto, respetar los límites y permisos de ese producto; no ampliar ámbito ni retirar filtros automáticamente ante resultados vacíos.
- Vincular una validación con el comportamiento o acción que realmente comprueba. La existencia de código, una prueba de carga o una declaración de éxito no sustituye evidencia funcional pertinente.
- Mantener independientes las instrucciones globales de Copilot y las instrucciones/skills del producto. La existencia de un archivo no demuestra que una sesión de Side Chat lo haya cargado o ejecutado.

## Límites de la evidencia

**Perfil operativo:** el archivo referenciado arriba se publicó en `parroyol/OficinaIA`, rama `main`, commit `e65ab31`. Esto acredita disponibilidad del documento en ese repositorio; no demuestra por sí solo su activación automática en cada superficie de Copilot.

**Context-On-Demand:** los registros de las sesiones de implementación describen comprobaciones CLI con datos sintéticos y pruebas dirigidas. También indican que no quedó acreditado el flujo completo Copilot → descubrimiento/activación de la skill → decisión de recuperar → respuesta de Side Chat. Por tanto, no describirlo como una integración nativa E2E probada.

**Trazabilidad operativa:** el piloto registró una cadena con relaciones parciales; se ejecutaron dos pruebas E2E de carga/presencia de elementos, pero faltaron la búsqueda funcional asociada y su validación posterior. El estado registrado fue **VALIDADO CON RESERVAS**, no validación funcional completa.

**Instrucciones globales de la app:** la configuración de “App instructions” se propuso como mecanismo global; no se observó su configuración ni una prueba de arranque de un Side Chat nuevo que confirmase su aplicación. No afirmar que el dispatcher global ya está activo.

## Registro de fuentes y distribución

- `docs/perfil-operativo.md`: publicado en este repositorio central.
- `docs/gestion-contextual-bajo-demanda.md`, `.github/copilot-instructions.md` y `.github/skills/context-on-demand/SKILL.md`: observados en worktrees de OficinaAI; su publicación e integración en la rama principal no quedan acreditadas por esta síntesis.
- `PRACTICA-OPERATIVA-OBSERVADA.md` y documentos del piloto: observados en el worktree de auditoría; no se consideran distribuidos por el hecho de resumirse aquí.

Esta guía es un mapa de reutilización y límites conocidos. Para cambiar el comportamiento de un producto, verificar primero sus archivos e instrucciones vigentes en el checkout correspondiente; no copiar una decisión de una línea de trabajo a otra sin comprobar su alcance.
