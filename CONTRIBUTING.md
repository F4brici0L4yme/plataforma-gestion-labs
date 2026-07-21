# Guía de Contribución

Gracias por colaborar en la Plataforma Híbrida de Gestión de Laboratorios de Computación.

Este documento explica cómo participar, cómo proponer cambios y cómo se revisan.

## Antes de empezar

Lee el README del proyecto.

Lee el archivo CODE_OF_CONDUCT.md.

Si tienes dudas sobre una tarea, pregunta antes de asumir.

## Requisitos

Cuenta de GitHub o GitLab con acceso al repositorio.

Git instalado en tu computadora.

## Cómo clonar el repositorio

```
git clone <URL-del-repositorio>
```

```
cd <nombre-del-repositorio>
```

## Flujo de ramas

La rama `main` siempre debe estar estable.

La rama `develop` se usa para integrar trabajo en curso.

Cada tarea se trabaja en su propia rama.

Nombra tu rama así:

```
feature/<squad>-<tarea-corta>
```

Ejemplo:

```
feature/persona-e-contributing
```

## Cómo crear tu rama de trabajo

```
git checkout develop
```

```
git pull origin develop
```

```
git checkout -b feature/persona-e-contributing
```

## Convención de commits

Usa mensajes de commit cortos y claros.

Antepone un prefijo según el tipo de cambio.

`feat:` para una funcionalidad nueva.

`fix:` para una corrección.

`docs:` para cambios en documentación.

`chore:` para tareas de mantenimiento.

Ejemplo:

```
git commit -m "docs: agrega CONTRIBUTING.md"
```

## Cómo subir tus cambios

```
git add .
```

```
git commit -m "docs: agrega CONTRIBUTING.md"
```

```
git push origin feature/persona-e-contributing
```

## Cómo abrir un Pull Request

Abre un Pull Request desde tu rama hacia `develop`.

Escribe un título claro y corto.

En la descripción indica qué archivo agregas o modificas.

En la descripción indica de qué tarea del reparto se trata.

Si tu tarea depende de otra, dilo en la descripción.

Asigna como revisor al Tech Lead o al Chapter Lead correspondiente.

Espera al menos una aprobación antes de hacer merge.

No hagas merge de tu propio Pull Request sin revisión.

## Cómo reportar un problema

Abre un Issue en el repositorio.

Describe qué esperabas que pasara.

Describe qué pasó en realidad.

Indica los pasos para reproducir el problema si aplica.

Menciona a la persona responsable del área si la conoces.

## Cómo revisar el trabajo de otra persona

Comenta sobre partes específicas, no de forma general.

Indica exactamente qué falta o qué corregir.

Si todo está correcto, aprueba el Pull Request con un comentario breve.

## Buenas prácticas generales

Un Pull Request debe tratar un solo tema.

Evita mezclar varias tareas en un mismo Pull Request.

Actualiza tu rama con `develop` antes de pedir revisión.

```
git checkout feature/persona-e-contributing
```

```
git pull origin develop
```

## Contacto

Si tienes dudas, escribe al Tech Lead del squad.

Si la duda es sobre el proyecto en general, escribe al Chapter Lead.
