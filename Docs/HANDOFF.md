# HANDOFF: léelo primero

> **Chat nuevo: antes de hacer cualquier cosa** debes:
> 1. Leer este documento completo.
> 2. Leer [README.md](README.md) (el MD padre) y **todos** los MD que enlaza, bajando hasta el último MD de mecánica.
> 3. Decirle al usuario, en español y en 3 a 6 líneas, qué entendiste: qué juego es, qué existe, qué está en curso y qué sigue. Pregunta lo que no cuadre.
>
> Solo después de eso empiezas a trabajar.

**Última actualización:** 2026-11-12 (chat 1, inicio del proyecto)

## Dónde quedamos

- Se creó el repo `C:\Users\nmore\Documents\Woodsbrow` con un proyecto Unity vacío (rama `main`, primer commit `5f0f456`). Se creó con 6000.6.2f1 y después se movió a `Documents` y se pasó a **6000.6.9f1**: Unity actualiza `ProjectSettings/ProjectVersion.txt` la primera vez que lo abre con esa versión.
- Se agregó MCP for Unity: el paquete `com.coplaydev.unity-mcp` en `Packages/manifest.json` y el servidor en `.mcp.json`.
- Se armó la estructura de documentación: `CLAUDE.md`, este handoff, el MD padre, `ESTADO.md`, el índice de mecánicas con su plantilla y `Contexto/`.
- **Todavía no hay diseño del juego.** El usuario lo va a explicar.

## Decisiones tomadas

| Fecha | Decisión |
|---|---|
| 2026-11-12 | Proyecto nuevo e independiente de Cumplea-os, con su propio repo (no es una rama) |
| 2026-11-12 | Unity 6000.6.9f1 (Unity 6.6, se partió con 6000.6.2f1) |
| 2026-11-12 | Conectado a MCP for Unity |
| 2026-11-12 | Todo se documenta en MD: un MD padre que enlaza índices y un MD por mecánica |
| 2026-11-12 | Claude avisa cuando queda poco contexto y deja este handoff actualizado |

## Próximo paso exacto

1. El usuario abre el proyecto en Unity (Unity Hub → *Add project from disk*) para que se instale el paquete MCP, y verifica en *Window → MCP for Unity* que esté conectado.
2. El usuario publica el repo en GitHub desde GitKraken.
3. El usuario explica la idea del juego → se llena el MD padre y se crean los primeros MD de mecánicas.

## Preguntas abiertas

- ¿Qué juego es? (género, concepto, loop principal, estilo visual, 2D/3D)
- ¿Pipeline de render (Built-in, URP 2D, URP 3D)? Depende del punto anterior.
- ¿Se usa Odin Inspector como en Cumplea-os?

## Historial de chats

| Chat | Fecha | Qué se hizo |
|---|---|---|
| 1 | 2026-11-12 | Creación del repo y del proyecto Unity, MCP, estructura de documentación |
