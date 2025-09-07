# SmartEdify-Planner — Configuración de actualización por agente

Este archivo documenta cómo este agente (y cualquier colaborador) debe actualizar el repositorio `egomez11/SmartEdify-Planner` desde esta carpeta de trabajo.

## Repositorio y ramas
- Remoto: `origin`
- URL: `https://github.com/egomez11/SmartEdify-Planner.git`
- Rama por defecto: `main`

## Prerrequisitos
- Git instalado y configurado (usuario y email).
- Sesión autenticada con GitHub CLI: `gh auth status` (si no, `gh auth login`).

## Flujos de actualización

### 1) Actualización directa a main (rápida)
Usar solo para cambios pequeños y acordados.

```bash
# Ver estado y qué se va a subir
git status

# Añadir cambios y hacer commit (usa Conventional Commits)
# ejemplos: feat:, fix:, docs:, chore:, refactor:, test:
git add -A
git commit -m "chore: update AGENTE.md and maintenance docs"

# Alinear con remoto y empujar
git pull --rebase origin main
git push -u origin main
```

### 2) Rama de funcionalidad + Pull Request (recomendado)
Para cambios medianos/grandes o revisiones.

```bash
# Crear rama
BR="feature/<descripcion-corta>"
git checkout -b "$BR"

# Commit(s)
git add -A
git commit -m "feat: <resumen del cambio>"

# Publicar rama y abrir PR
git push -u origin "$BR"
# si usas GitHub CLI:
gh pr create --fill --base main --head "$BR"

# Tras aprobar/mergear, limpiar
# (opcional) gh pr merge --squash --delete-branch
```

## Convenciones de commit
- Usar Conventional Commits: `feat:`, `fix:`, `docs:`, `chore:`, `refactor:`, `test:`.
- Mensaje en imperativo, breve y claro.

## Sincronización y conflictos
```bash
git fetch origin
git checkout main
git pull --rebase origin main
```
Si aparecen conflictos, resolver archivos, luego:
```bash
git add <archivo(s)>
git rebase --continue
```

## Notas de seguridad
- No subir secretos/llaves `.env`, tokens ni credenciales. Añadir a `.gitignore` si corresponde.
- Mantener el mínimo de permisos en tokens/CLI (fine-grained tokens si se usan).

## Mantenimiento opcional
- Normalización EOL: añadir `.gitattributes` con `* text=auto` para evitar avisos CRLF/LF.
- `.gitignore` ajustado a tecnologías usadas (Node/VSCode/JetBrains/etc.).

---
Documento mantenido por: agente de automatización (Codex CLI)
