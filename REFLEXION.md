# REFLEXION — FASE 3

## Opción elegida: Opción A — Múltiples tags en un solo pipeline

Se creó una nueva versión de la aplicación modificando el archivo index.html, lo que permitió diferenciar visualmente la versión anterior (v1.0.0) de la nueva (v1.1.0). Luego se realizó un commit y se creó el nuevo tag v1.1.0. Al ejecutar el pipeline, se generó y publicó una nueva imagen en el registry. 

### ¿Cuándo sería peligroso usar siempre `latest` en producción?

Usar `latest` en producción puede ser peligroso porque cada vez que se despliega, no hay garantía de que se esté utilizando la misma versión de la aplicación. Si una nueva versión tiene errores, podría afectar directamente a los usuarios sin control previo. Además, dificulta el control de errores, y la ejecución de un rollback, ya que no se tiene una referencia clara de qué versión estaba funcionando correctamente.

---


### 1. ¿Qué ventaja tiene disparar el pipeline con un tag en lugar de con cada push?

Disparar el pipeline con un tag permite tener mayor control sobre las versiones que se construyen y publican. En lugar de generar una imagen por cada cambio lo cual puede ser innecesario y generar costos de procesamiento. Al disparar con la versión estamos seguros que es la versión final que vamos a utilizar para ese release. Así también se mejora la trazabilidad y reportería.

---

### 2. ¿Cuál es la diferencia entre usar `latest` y una versión específica como `1.0.0` en producción?

Si se utiliza latest implica que siempre se desplegará la última versión disponible, lo cual puede ser útil en entornos de desarrollo o testing. En estos ambientes, siempre necesitamos tener una versión actualziada para pruebas EN producción, necesitamos la última versión estable y probada como por ejemplo 1.0.0 lo cual permite tener estabilidad y control de la versión actual. De esa manera se evita cambios inesperados



---

### 3. El proyecto anterior ya tenía 6 tags creados. ¿Qué significaría haber tenido este workflow desde el principio?

Significaría que se podría tener desde el inicio un historial de todas las versiones que se pueden desplegar, así mismo podremos hacer rollback o elegir la versión estable que necesitamos. Esto permite una gestión más eficiente del ciclo de vida de la aplicación.

---
