# REFLEXION — FASE 3

## Opción elegida: Opción A — Múltiples tags en un solo pipeline

Se creó una nueva versión de la aplicación modificando el archivo `index.html`, lo que permitió diferenciar visualmente la versión anterior (`v1.0.0`) de la nueva (`v1.1.0`). Luego se realizó un commit y se creó el nuevo tag `v1.1.0`. Al ejecutar el pipeline, se generó y publicó una nueva imagen en el registry. 

### ¿Cuándo sería peligroso usar siempre `latest` en producción?

Usar `latest` en producción puede ser peligroso porque introduce incertidumbre. Cada vez que se despliega, no hay garantía de que se esté utilizando la misma versión de la aplicación. Si una nueva versión tiene errores, podría afectar directamente a los usuarios sin control previo. Además, dificulta el rollback, ya que no se tiene una referencia clara de qué versión estaba funcionando correctamente.

---

## Reflexión

### 1. ¿Qué ventaja tiene disparar el pipeline con un tag en lugar de con cada push?

Disparar el pipeline con un tag permite tener mayor control sobre las versiones que se construyen y publican. En lugar de generar una imagen por cada cambio (lo cual puede ser innecesario y costoso), solo se generan versiones cuando se considera que el código está listo para ser liberado.

Esto cambia el flujo de trabajo del equipo hacia un modelo más organizado basado en versionado semántico, donde cada release está claramente identificado. También mejora la trazabilidad y facilita auditorías o despliegues controlados.

---

### 2. ¿Cuál es la diferencia entre usar `latest` y una versión específica como `1.0.0` en producción?

La principal diferencia es la previsibilidad.

* Usar `latest` implica que siempre se desplegará la última versión disponible, lo cual puede ser útil en entornos de desarrollo o testing, pero riesgoso en producción.
* Usar una versión específica como `1.0.0` garantiza que siempre se ejecuta exactamente la misma versión, lo que permite mayor estabilidad, control y facilidad para hacer rollback en caso de fallos.

En producción, es una buena práctica usar versiones específicas para evitar cambios inesperados.

---

### 3. El proyecto anterior ya tenía 6 tags creados. ¿Qué significaría haber tenido este workflow desde el principio?

Si este workflow hubiera estado implementado desde el inicio, cada uno de esos tags habría generado automáticamente una imagen versionada en el registry. Esto significaría:

* Tener un historial completo de versiones listas para desplegar.
* Poder hacer rollback fácilmente a cualquier versión anterior.
* Mejor trazabilidad entre código y artefactos desplegables.
* Mayor madurez en el proceso de CI/CD del proyecto.

En general, habría permitido una gestión más profesional y eficiente del ciclo de vida de la aplicación.

---
