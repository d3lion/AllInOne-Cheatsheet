# Git <img src="https://victorroblesweb.es/wp-content/uploads/2018/04/git.png" alt="Git Logo" width="50">

<p align="center">
  <img src="https://somebooks.es/wp-content/uploads/2023/12/git-b.png" alt="Git Logo">
</p>

Git es un sistema de control de versiones distribuido, gratuito y de código abierto, diseñado para manejar todo tipo de proyectos con velocidad y eficiencia. Git permite a los equipos de desarrollo colaborar y realizar un seguimiento de los cambios en el código fuente durante el desarrollo de software. Su objetivo es la simplicidad, velocidad y una fuerte compatibilidad con el desarrollo no lineal y distribuido. 🚀

## Índice 📚

- [Configuración Inicial](#configuración-inicial)
- [Crear un Repositorio](#crear-un-repositorio)
- [Operaciones Básicas](#operaciones-básicas)
- [Trabajando con Ramas](#trabajando-con-ramas)
- [Fusionar Ramas](#fusionar-ramas)
- [Remotos](#remotos)
- [Revertir Cambios](#revertir-cambios)
- [Stash](#stash)
- [Etiquetas (Tags)](#etiquetas-tags)
- [Ayuda](#ayuda)
- [Instalación](#instalación)
- [Características](#características)
- [Recursos Adicionales](#recursos-adicionales)
- [Contribuciones](#contribuciones)
- [Licencia](#licencia)

## Instalación 🛠️

### En Windows 🪟

1. Descarga el instalador de Git desde [git-scm.com](https://git-scm.com/download/win).
2. Ejecuta el instalador y sigue las instrucciones.

### En macOS 🍏

```bash
# Usando Homebrew
brew install git
```

### En Linux 🐧

```bash
# En distribuciones basadas en Debian (como Ubuntu)
sudo apt-get update
sudo apt-get install git

# En distribuciones basadas en RPM (como Fedora)
sudo dnf install git
```

## Características ✨

1. **Distribuido**: Cada desarrollador tiene una copia completa del historial del proyecto.
2. **Rápido**: Las operaciones locales son rápidas debido a que no dependen de una conexión de red.
3. **Seguro**: Utiliza SHA1 para nombrar y identificar objetos en su base de datos.
4. **Ramas y fusiones**: Soporta ramas y fusiones eficientes, permitiendo un desarrollo no lineal.
5. **Desarrollo colaborativo**: Facilita la colaboración entre múltiples desarrolladores.

## Configuración Inicial ⚙️

```bash
# Configurar el nombre de usuario
git config --global user.name "Tu Nombre"

# Configurar el email de usuario
git config --global user.email "tuemail@example.com"
```

## Crear un Repositorio 📂

```bash
# Inicializar un nuevo repositorio
git init

# Clonar un repositorio existente
git clone https://github.com/usuario/repositorio.git
```

## Operaciones Básicas 🔧

```bash
# Ver el estado del repositorio
git status

# Añadir archivos al staging area
git add nombre_del_archivo

# Añadir todos los archivos al staging area
git add .

# Hacer un commit
git commit -m "Mensaje del commit"

# Ver el historial de commits
git log
```

## Trabajando con Ramas 🌿

```bash
# Listar todas las ramas
git branch

# Crear una nueva rama
git branch nombre_de_la_rama

# Cambiar a una rama existente
git checkout nombre_de_la_rama

# Crear y cambiar a una nueva rama
git checkout -b nombre_de_la_rama

# Eliminar una rama
git branch -d nombre_de_la_rama
```

## Fusionar Ramas 🔀

```bash
# Fusionar una rama a la rama actual
git merge nombre_de_la_rama
```

## Remotos 🌐

```bash
# Ver los remotos configurados
git remote -v

# Añadir un nuevo remoto
git remote add nombre_remoto https://github.com/usuario/repositorio.git

# Eliminar un remoto
git remote remove nombre_remoto

# Obtener los cambios del remoto
git fetch nombre_remoto

# Obtener y fusionar cambios del remoto
git pull nombre_remoto nombre_de_la_rama

# Enviar cambios al remoto
git push nombre_remoto nombre_de_la_rama
```

## Revertir Cambios 🔄

```bash
# Descartar cambios en un archivo
git checkout -- nombre_del_archivo

# Revertir un commit
git revert id_del_commit

# Resetear al estado de un commit anterior
git reset --hard id_del_commit
```

## Stash 🗃️

```bash
# Guardar cambios sin hacer commit
git stash

# Ver los stashes guardados
git stash list

# Aplicar el stash más reciente
git stash apply

# Aplicar y eliminar el stash más reciente
git stash pop

# Eliminar un stash específico
git stash drop stash@{n}
```

## Etiquetas (Tags) 🏷️

```bash
# Crear una nueva etiqueta
git tag -a v1.0 -m "Versión 1.0"

# Listar todas las etiquetas
git tag

# Eliminar una etiqueta
git tag -d v1.0

# Enviar etiquetas al remoto
git push nombre_remoto --tags
```

## Ayuda ❓

```bash
# Obtener ayuda sobre un comando específico
git help nombre_del_comando
```

## Recursos Adicionales 📚

- [Documentación oficial de Git](https://git-scm.com/doc)
- [Pro Git Book](https://git-scm.com/book/en/v2)
- [Tutorial de Git](https://www.atlassian.com/git/tutorials)

## Contribuciones 🤝

¡Las contribuciones son bienvenidas! Si deseas contribuir, por favor sigue estos pasos:

1. Haz un fork del repositorio.
2. Crea una nueva rama (`git checkout -b feature/nueva-caracteristica`).
3. Realiza tus cambios y haz commit (`git commit -am 'Añadir nueva característica'`).
4. Envía tus cambios a tu repositorio fork (`git push origin feature/nueva-caracteristica`).
5. Abre un Pull Request.

## Licencia 📄

Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo [LICENSE](LICENSE) para obtener más información.
