# Centro de Mando — Jorge (NT / GF)

Dashboard personal de control y registro de tiempo. Una pantalla, dos monitores.

## Arquitectura (etapa de evaluación)
- **Frontend:** este repo, servido por **GitHub Pages** (estático, sin downtime).
- **Datos / Auth:** **Supabase** (proyecto host de evaluación `Docusafe`, tablas `cmd_*` con RLS por email).
- **Seguridad:** solo `jorge@naturaltrade.ca` puede leer/escribir (RLS `cmd_is_owner()`); el frontend solo lleva la llave *publishable* (segura para exponer). El histórico de tiempo (`cmd_time_entry`) es **inmutable** (sin delete).
- **Respaldo:** snapshot nocturno a repo privado (ver `nt-command-center-backups`).

## Secciones
- **Mis Pendientes** — agregar → ▶ iniciar (cronómetro) → ✓ terminar (registra tiempo). Un timer activo a la vez.
- **Proyectos** — 18 proyectos en 7 dominios, con pendientes y tiempo del día.
- **Avisos de correo** — bandeja Gmail (fase 2).
- **Accesos NetSuite** — deep-links editables (clic para configurar el URL).
- **OTROS** — botón grande para medir distracciones aparte; calcula % productivo.

## Config
Editar `SB_URL` / `SB_KEY` / `OWNER` al inicio del `<script>` en `index.html` si se migra a un proyecto Supabase dedicado.
