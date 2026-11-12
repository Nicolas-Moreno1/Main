# Woodsbrow: documento padre

> Este es el **MD padre** del proyecto: desde aquí se llega a todos los demás MD. Si algo existe en el juego, tiene un MD y ese MD está enlazado desde aquí (directamente o a través del índice de su sección).
> Si eres un chat nuevo: lee primero [HANDOFF.md](HANDOFF.md) y después todos los MD de este árbol (ver `CLAUDE.md`).

## El juego en corto

**Woodsbrow** es un nombre provisorio. El diseño todavía no está definido: esta sección se llena cuando el usuario explique la idea (género, concepto, loop principal, estilo).

| | |
|---|---|
| Motor | Unity 6000.6.9f1 |
| Repositorio | `C:\Users\nmore\Documents\Woodsbrow` (rama `main`) |
| Estado | Proyecto vacío, recién creado (2026-11-12) |

## Mapa de documentación

| Documento | Qué tiene |
|---|---|
| [HANDOFF.md](HANDOFF.md) | Dónde quedó el último chat y qué sigue. **Lo primero que lee un chat nuevo.** |
| [ESTADO.md](ESTADO.md) | Estado actual: qué existe, qué está en curso, próximos pasos, preguntas abiertas |
| [Mecanicas/README.md](Mecanicas/README.md) | Índice de mecánicas: un MD por mecánica |
| [Contexto/README.md](Contexto/README.md) | Todo lo que el usuario mandó (imágenes, PDF, referencias) |
| [`../CLAUDE.md`](../CLAUDE.md) | Reglas de trabajo para Claude (se carga solo en cada chat) |

Cuando aparezcan otras secciones (sistemas, UI, arte, audio, niveles...), cada una tendrá su carpeta con un `README.md` índice y se agrega a esta tabla.

## Cómo se documenta

- **Un MD por mecánica o sistema**, con la plantilla [Mecanicas/_PLANTILLA.md](Mecanicas/_PLANTILLA.md).
- Cada MD termina con **Interacciones**: con qué otras mecánicas o sistemas se conecta, con enlaces.
- Cuando algo cambia, se actualiza su MD, los que interactúan con él y los índices.
- `Docs/` va en español; el código y los textos del juego, en inglés.
