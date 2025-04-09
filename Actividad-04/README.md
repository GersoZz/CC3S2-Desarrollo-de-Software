# User info

![git config](./images/1-datos.png)


# git log

![git log](./images/2-log.png)


### git log --graph --pretty=format:'%x09 %h %ar ("%an") %s'

![git log --graph --pretty=format:'%x09 %h %ar ("%an") %s'](./images/3-log_v2.png)

### git log --oneline

![git log --oneline](./images/4-log_oneline.png)


## Crear una rama desde una rama específica

![git checkout -b](./images/5-branch.png)


# Preguntas

### ¿Cómo te ha ayudado Git a mantener un historial claro y organizado de tus cambios?

Cada progreso que hago en mi código lo registro mediante un commit. Si más adelante me doy cuenta que cierta feature está fallando, puedo revisar exacatmente el commit donde hice ese cambio y corregirlo facilmente.

### ¿Qué beneficios ves en el uso de ramas para desarrollar nuevas características o corregir errores?

Es útil para separar el código que se va a usar en los dintintos ambientes: Producción, Pruebas, Desarrollo. De esta forma nos aseguramos que el código que se usa en producción sea lo mejor posible.

### Realiza una revisión final del historial de commits para asegurarte de que todos los cambios se han registrado correctamente.

Todo ok

![git log --oneline](./images/6-log.png)

### Revisa el uso de ramas y merges para ver cómo Git maneja múltiples líneas de desarrollo.

En efecto, sí.

![git log --oneline](./images/7-branches.png)

# Ejercicios

### Resolver conflictos 

Conflicto

![alt text](./images/8-conflict.png)

Resolucion del conflicto

![alt text](./images/9-conflict_solve.png)

Merge y borrar rama

![merge](./images/10-merge.png)


## Ejercicio 2: Exploración y manipulación del historial de commits

### Ver el historial detallado de commits:

```bash
git log -p
```

![git log -p](./images/11-log_p.png)


### Filtrar commits por autor

```bash
git log --author="GersoZz"
```

![git log --author](./images/12-log_author.png)
