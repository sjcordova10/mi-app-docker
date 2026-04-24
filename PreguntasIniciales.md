# REFLEXIÓN — Preguntas iniciale

## 1. Diferencia entre Máquina Virtual y contenedor Docker

Una VM incluye un sistema operativo completo, por lo que consume más recursos y tarda más en iniciar, por tanto es más pesado.
Un contenedor comparte el sistema operativo del host, siendo mucho más rápido y eficiente.


---

## 2. ¿Por qué los contenedores son "ligeros"?

Porque no incluyen un sistema operativo completo, solo la app y sus dependencias.
Comparten el kernel del host, reduciendo consumo de recursos lo cual permite arrancar rápido y ejecutar más instancias.

---

## 3. Comandos y su función

* `docker run` → Ejecuta un contenedor
* `docker ps` → Lista los contenedores activos
* `docker stop` → Detiene el contenedor
* `docker rm` → Elimina el contenedor

---
