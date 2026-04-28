# Recuperación de archivo borrado por error

## Error simulado

En esta práctica simulé el borrado accidental del archivo `errores.sh`.
Primero creé el archivo y lo añadí al repositorio mediante un commit.
Después lo eliminé con el comando `rm errores.sh` y confirmé ese borrado con otro commit, simulando así un error real en un entorno de trabajo.

## Proceso de recuperación del archivo

Para recuperar el archivo eliminado, seguí los siguientes pasos:

1. Consulté el historial de commits para identificar el estado anterior al borrado:

```bash
git log --oneline
```

2. Revisé el historial de acciones recientes del repositorio:

```bash
git reflog
```

3. Recuperé el archivo desde el commit anterior al borrado:

```bash
git checkout HEAD~1 -- errores.sh
```

4. Verifiqué que el archivo se había recuperado correctamente:

```bash
ls
git status
```

5. Guardé la recuperación en el repositorio mediante un nuevo commit:

```bash
git add errores.sh
git commit -m "Recuperar errores.sh tras borrado accidental"
```

## Comandos utilizados

### Crear el archivo

```bash
nano errores.sh
git add errores.sh
git commit -m "Añadir archivo errores.sh"
```

### Simular el error

```bash
rm errores.sh
git add .
git commit -m "Borrar errores.sh por error"
```

### Recuperar el archivo

```bash
git checkout HEAD~1 -- errores.sh
git add errores.sh
git commit -m "Recuperar errores.sh tras borrado accidental"
```

## Aprendizaje

Con esta práctica he aprendido que Git permite recuperar archivos borrados incluso después de haber confirmado su eliminación con un commit.
