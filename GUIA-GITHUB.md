# 🚀 Guía: Publicar Torre de Control en GitHub

## 📋 Pre-requisitos

- ✅ Cuenta de GitHub (gratuita)
- ✅ Git instalado en tu computador
- ✅ Los archivos del repositorio descargados

---

## 🎯 Opción 1: Publicar con GitHub Desktop (Más Fácil)

### Paso 1: Instalar GitHub Desktop
1. Descarga desde: https://desktop.github.com/
2. Instala y abre la aplicación
3. Inicia sesión con tu cuenta de GitHub

### Paso 2: Crear Repositorio
1. Click en "File" → "New Repository"
2. Nombre: `marine-farm-torre`
3. Descripción: `Torre de Control - Gestión de Exportaciones`
4. Ruta: Selecciona la carpeta donde descargaste los archivos
5. Click "Create Repository"

### Paso 3: Publicar
1. Click en "Publish repository"
2. Desmarca "Keep this code private" (si quieres que sea público)
3. Click "Publish repository"

### Paso 4: Activar GitHub Pages
1. Ve a tu repositorio en GitHub.com
2. Settings → Pages
3. Source: `Deploy from a branch`
4. Branch: `main` → Folder: `/root`
5. Save

¡Listo! Tu app estará en: `https://tu-usuario.github.io/marine-farm-torre/`

---

## 🎯 Opción 2: Publicar con Terminal (Para Desarrolladores)

### Paso 1: Crear Repositorio en GitHub.com

1. Ve a https://github.com/new
2. Repository name: `marine-farm-torre`
3. Description: `Torre de Control - Gestión de Exportaciones`
4. Selecciona: Public o Private
5. **NO** marques "Initialize with README"
6. Click "Create repository"

### Paso 2: Inicializar Git Local

Abre tu terminal y navega a la carpeta con los archivos:

```bash
cd ~/Downloads/marine-farm-torre
# o la carpeta donde tengas los archivos

# Verificar que los archivos estén ahí
ls -la
# Debes ver: index.html, logo-white.png, logo-blue.png, README.md, etc.

# Inicializar repositorio Git
git init

# Agregar todos los archivos
git add .

# Crear primer commit
git commit -m "Initial commit: Torre de Control v1.0"
```

### Paso 3: Conectar con GitHub

Reemplaza `TU-USUARIO` con tu usuario de GitHub:

```bash
# Agregar repositorio remoto
git remote add origin https://github.com/TU-USUARIO/marine-farm-torre.git

# Verificar que se agregó correctamente
git remote -v

# Subir los archivos
git branch -M main
git push -u origin main
```

Si te pide credenciales:
- Usuario: tu usuario de GitHub
- Password: usa un Personal Access Token (no tu contraseña)

### Paso 4: Crear Personal Access Token (si es necesario)

1. Ve a GitHub.com → Settings (tu perfil)
2. Developer settings → Personal access tokens → Tokens (classic)
3. "Generate new token (classic)"
4. Nombre: `Torre Control Token`
5. Expiration: 90 days
6. Selecciona: `repo` (todos los permisos de repositorio)
7. Click "Generate token"
8. **COPIA EL TOKEN** (no podrás verlo de nuevo)
9. Úsalo como password al hacer `git push`

### Paso 5: Activar GitHub Pages

```bash
# Ir a tu repositorio en el navegador
# Formato: https://github.com/TU-USUARIO/marine-farm-torre

# Settings → Pages
# Source: Deploy from a branch
# Branch: main → Folder: /root
# Save
```

Espera 1-2 minutos y tu app estará en:
```
https://TU-USUARIO.github.io/marine-farm-torre/
```

---

## 🎯 Opción 3: Arrastrar y Soltar (Ultra Fácil)

### Método A: Usar GitHub Web Interface

1. Ve a https://github.com/new
2. Crea el repositorio: `marine-farm-torre`
3. Una vez creado, click en "uploading an existing file"
4. Arrastra los archivos: index.html, logos, README.md, etc.
5. Escribe mensaje: "Initial commit"
6. Click "Commit changes"
7. Activa GitHub Pages (Settings → Pages)

---

## 🔄 Actualizar el Repositorio (Cambios Futuros)

### Con GitHub Desktop:
1. Abre GitHub Desktop
2. Verás los cambios en "Changes"
3. Escribe mensaje de commit
4. Click "Commit to main"
5. Click "Push origin"

### Con Terminal:
```bash
# Ver archivos modificados
git status

# Agregar cambios
git add .

# Crear commit
git commit -m "Descripción de los cambios"

# Subir a GitHub
git push
```

---

## 🌐 URLs del Proyecto

Una vez publicado, tendrás:

**Repositorio:**
```
https://github.com/TU-USUARIO/marine-farm-torre
```

**Aplicación en vivo (GitHub Pages):**
```
https://TU-USUARIO.github.io/marine-farm-torre/
```

**Clonar el repositorio:**
```bash
git clone https://github.com/TU-USUARIO/marine-farm-torre.git
```

---

## 🔒 Repositorio Privado vs Público

### Público (Recomendado si no hay datos sensibles)
- ✅ Gratis
- ✅ GitHub Pages gratis
- ✅ Fácil compartir con el equipo
- ⚠️ Cualquiera puede ver el código

### Privado (Si hay datos confidenciales)
- ✅ Solo tu equipo puede ver
- ✅ Gratis en GitHub
- ⚠️ GitHub Pages requiere plan pago
- 💡 Alternativa: usar Netlify/Vercel (gratis y privado)

---

## 🎁 Bonus: Hacer el Repositorio más Profesional

### Agregar Badge al README

Edita `README.md` y actualiza los badges:

```markdown
[![GitHub Pages](https://img.shields.io/badge/demo-live-success)](https://TU-USUARIO.github.io/marine-farm-torre/)
[![GitHub](https://img.shields.io/github/license/TU-USUARIO/marine-farm-torre)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-blue)](https://github.com/TU-USUARIO/marine-farm-torre/releases)
```

### Agregar Screenshots

1. Toma capturas de pantalla de tu app
2. Súbelas a una carpeta `docs/screenshots/`
3. Reemplaza los placeholders en README.md:

```markdown
![Dashboard](docs/screenshots/dashboard.png)
```

### Crear Release

En GitHub:
1. Releases → "Create a new release"
2. Tag: `v1.0.0`
3. Title: `Torre de Control v1.0.0`
4. Descripción: Lista de características
5. Publish release

---

## 🐛 Solución de Problemas

### Error: "Permission denied (publickey)"
```bash
# Usar HTTPS en lugar de SSH
git remote set-url origin https://github.com/TU-USUARIO/marine-farm-torre.git
```

### Error: "failed to push some refs"
```bash
# Forzar push (solo si es tu primer push)
git push -u origin main --force
```

### Los logos no se ven en GitHub Pages
- Verifica que los archivos `logo-white.png` y `logo-blue.png` estén en la raíz
- Verifica mayúsculas/minúsculas en los nombres de archivo
- Espera 5-10 minutos para que GitHub Pages se actualice

### No aparece el sitio en GitHub Pages
- Espera 2-5 minutos después de activar Pages
- Verifica que el archivo se llame `index.html` (no `torre-control.html`)
- Verifica que esté en la rama `main`

---

## 📞 ¿Necesitas Ayuda?

Si tienes problemas:

1. **Documentación de GitHub Pages:**
   https://docs.github.com/pages

2. **GitHub Community:**
   https://github.community/

3. **Video Tutorial (español):**
   Busca en YouTube: "como subir proyecto a github"

---

## ✅ Checklist Final

Antes de compartir la URL con tu equipo:

- [ ] Repositorio creado en GitHub
- [ ] Todos los archivos subidos (index.html + logos + README)
- [ ] GitHub Pages activado
- [ ] URL funciona: `https://TU-USUARIO.github.io/marine-farm-torre/`
- [ ] Logos se ven correctamente
- [ ] Datos de prueba funcionan
- [ ] LocalStorage funciona (probar crear solicitud, refrescar, debe persistir)

---

## 🎉 ¡Felicitaciones!

Tu Torre de Control ahora está en GitHub y accesible desde cualquier lugar.

**Comparte la URL con tu equipo:**
```
https://TU-USUARIO.github.io/marine-farm-torre/
```

---

**¿Preguntas?** Abre un issue en el repositorio o contacta al desarrollador.
