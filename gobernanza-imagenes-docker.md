# Necesidad de Gobernanza de Imágenes Docker, Software y Licencias

## ¿Por qué hace falta gobernanza y no solo un catálogo técnico?

Tener un registro de imágenes (Harbor) resuelve el problema técnico de dónde guardar y descargar imágenes. Pero no resuelve por sí solo tres problemas de fondo que sí importan tanto en la universidad como en una empresa de software:

### 1. Trazabilidad

Sin gobernanza, cualquiera puede subir o modificar una imagen sin que quede claro quién lo hizo, cuándo y por qué. Esto es un riesgo porque:

- Si una imagen falla en producción (o en un examen/proyecto), no se puede saber qué cambió ni quién lo autorizó.
- No se puede auditar qué software exacto usó cada curso o cada proyecto en una fecha determinada.

Por eso el flujo del README incluye firma digital y aprobación antes de publicar: eso convierte un simple repositorio de archivos en un sistema con responsables identificables.

### 2. Licencias de software

Muchas imágenes incluyen software con licencias distintas (GPL, MIT, licencias comerciales, versiones "trial" o "educational"). Sin control:

- Una imagen académica podría terminar usándose en un contexto comercial sin la licencia adecuada.
- Se puede violar sin querer los términos de uso de una herramienta (por ejemplo, software con licencia solo para uso educativo).

La gobernanza obliga a que, antes de aprobar una imagen, alguien revise y documente qué licencias trae el software incluido.

### 3. Seguridad y vigencia

Una imagen aprobada hoy puede volverse insegura con el tiempo (vulnerabilidades descubiertas después). Sin un proceso de revisión periódica:

- Se siguen usando imágenes con fallas de seguridad conocidas.
- No hay fecha de expiración ni responsable de actualizar.

El escaneo automático (Trivy, mencionado en el README) cubre la parte técnica, pero la gobernanza define cada cuánto se vuelve a escanear una imagen ya publicada, no solo al momento de subirla.

## Qué debería incluir la gobernanza, en concreto

- Un responsable (rol, no persona) que aprueba cada imagen antes de publicarla.
- Un registro de qué licencias trae cada imagen y si son compatibles con el uso que se le va a dar (académico vs. comercial).
- Una política de expiración o revisión periódica de imágenes ya publicadas.
- Un historial de cambios por imagen (quién la creó, quién la modificó, cuándo).
- Reglas claras de qué pasa si una imagen tiene una vulnerabilidad crítica: se retira o se bloquea su descarga hasta corregirla.

## Por qué esto importa para el proyecto en particular

La plataforma tiene dos versiones: académica y empresarial. La gobernanza es lo que permite que ambas convivan con reglas distintas de exigencia (por ejemplo, la empresarial puede requerir aprobación de Seguridad además de la técnica) sin duplicar el sistema, solo ajustando el nivel de control según el contexto.

## Comentarios del grupo
```diff
- Rodrigo: Creo que la trazabilidad es lo más importante, sin saber quién aprobó qué imagen y cuándo, cualquier falla en un examen es difícil de auditar, muy importante para buscar al responsable y tener gobierno sobre los procesos dentro de nuestro proyecto.
- Sergio: De acuerdo con lo de Rodrigo, pero yo le sumaría el punto de seguridad y vigencia. En los diagramas de arquitectura que armé, Trivy aparece escaneando la imagen antes de publicarla, pero ese escaneo es solo al momento de subirla. Si la gobernanza no define cada cuánto se vuelve a escanear una imagen que ya está publicada, esa imagen puede pasar de segura a vulnerable con el tiempo y nadie se entera hasta que ya sea tarde. Para mí eso es tan importante como saber quién aprobó la imagen, porque de nada sirve saber quién aprobó si después nadie revisa que siga siendo segura.
```
