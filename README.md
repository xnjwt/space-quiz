# Órbita — Quiz de exploración espacial

Órbita es un quiz interactivo en español sobre exploración espacial. Incluye diez preguntas, seguimiento del progreso, explicaciones de las respuestas y temas claro y oscuro. Es una aplicación estática, autocontenida y sin dependencias: todo está en `index.html`.

## Ejecutar en local

Abre `index.html` directamente en un navegador. Si prefieres servirlo localmente, ejecuta desde la raíz del repositorio:

```sh
python3 -m http.server 8000
```

Después visita <http://localhost:8000>.

## Publicación

El workflow **Deploy to GitHub Pages** publica el contenido estático de la raíz del repositorio en GitHub Pages al actualizar `main`. También valida la creación del artefacto en las pull requests dirigidas a `main`.
