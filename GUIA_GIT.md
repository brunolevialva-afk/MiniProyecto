# Guía Completa de Git y GitHub (Desde Cero)

Esta guía les ayudará a configurar sus entornos, conectar su proyecto local con GitHub y trabajar en equipo para completar la tarea.

---

## Parte 0: Configuración Inicial de Git
Antes de empezar, cada uno debe configurar su identidad en su propia computadora. Abran una terminal (PowerShell o Git Bash) y ejecuten:

```bash
git config --global user.name "brunolevialva-afk"
git config --global user.email "brunolevialva@gmail.com"
```

---

## Parte 1: Crear el Repositorio en GitHub (Solo Alumno 1)
1. Entra a [github.com](https://github.com) e inicia sesión.
2. Haz clic en el botón **New** (o el icono **+**) para crear un nuevo repositorio.
3. Ponle de nombre `MiniProyecto`.
4. Déjalo como **Public** y **no** selecciones "Add a README" ni ".gitignore" (ya los crearemos localmente).
5. Haz clic en **Create repository**.

### Invitar al Alumno 2
1. En la página de tu repositorio en GitHub, ve a **Settings** > **Collaborators**.
2. Haz clic en **Add people** y busca el nombre de usuario o correo del Alumno 2.
3. El Alumno 2 debe revisar su correo o sus notificaciones de GitHub para **aceptar la invitación**.

---

## Parte 2: Conectar el Proyecto Local a GitHub
Si ya tienes la carpeta `MiniProyecto` creada por Antigravity (tu asistente):

### Para el Alumno 1:
Ejecuta estos comandos en la terminal dentro de la carpeta `MiniProyecto`:

```bash
# Cambiar el nombre de la rama principal a 'main' (estándar de GitHub)
git branch -M main

# Conectar con el repositorio remoto (reemplaza 'USUARIO' con tu nombre de GitHub)
git remote add origin https://github.com/USUARIO/MiniProyecto.git

# Subir el código inicial
git push -u origin main
```

### Para el Alumno 2:
En tu propia computadora, abre una terminal en la carpeta donde quieras guardar el proyecto y ejecuta:

```bash
git clone https://github.com/brunolevialva-afk/MiniProyecto.git
cd MiniProyecto
```

---

## Parte 3: Realizar la Tarea (Ramas y Cambios)

Sigan este flujo de trabajo para las 3 ramas (`rama1`, `rama2`, `rama3`).

### Alumno 1:
```bash
# Crear y subir las ramas si no existen en GitHub
git checkout -b rama1
git push origin rama1
# (Repite para rama2 y rama3)
```

### Ambos Alumnos (en cada rama):
1. **Moverse a la rama:** `git checkout rama1` (luego `git pull origin rama1` para estar al día).
2. **Hacer un cambio:** Abran `index.html`, añadan su nombre o un mensaje.
3. **Guardar y Subir:**
   ```bash
   git add index.html
   git commit -m "Cambio realizado por [Tu Nombre]"
   git push origin rama1
   ```
   

---

## Parte 4: Fusión Final (Merge)
Cuando ambos hayan terminado sus cambios en todas las ramas:

1. **Alumno 1** (en su computadora):
   ```bash
   git checkout main
   git merge rama1
   git merge rama2
   git merge rama3
   # Subir todo a GitHub
   git push origin main
   ```

2. **Alumno 2**:
   ```bash
   git checkout main
   git pull origin main
   ```

¡Listo! Ahora tienen el proyecto completo y sincronizado en GitHub.
