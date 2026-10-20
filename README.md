# Demo CI/CD

Pagina estatica usada para demostrar un pipeline de Integracion Continua / Despliegue Continuo con GitHub Actions y GitHub Pages.

## Como funciona el pipeline

Cada `push` a la rama `main` dispara `.github/workflows/ci-cd.yml`:

1. **test (CI)**: verifica que `index.html` exista y tenga una estructura HTML valida. Si falla, el pipeline se detiene aqui y no se despliega nada.
2. **build (CD)**: empaqueta el sitio como artefacto de GitHub Pages.
3. **deploy (CD)**: publica el artefacto en GitHub Pages automaticamente.

## Demo en vivo

1. Mostrar la pagina publicada (fondo azul, "Version 1").
2. Editar `index.html`: cambiar el texto a "Version 2" y el color de fondo.
3. `git add . && git commit -m "Version 2" && git push`.
4. Mostrar en la pestaña **Actions** de GitHub como corren los 3 jobs (test -> build -> deploy).
5. Recargar la pagina publicada: el cambio ya esta en produccion.

## Configuracion unica (antes del demo)

En GitHub, ir a **Settings -> Pages -> Source** y elegir **GitHub Actions** (no "Deploy from a branch").
