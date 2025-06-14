# 🛡️ File Activity Monitor - Mini EDR (Formación en Ciberseguridad)

Este proyecto es una herramienta **formativa** desarrollada para simular el comportamiento básico de un sistema EDR (Endpoint Detection and Response) enfocado en la **detección de keyloggers u otras actividades sospechosas relacionadas con archivos**.

> ⚠️ **Este proyecto no tiene ningún propósito comercial ni ofensivo. Está diseñado únicamente para fines educativos y en entornos controlados.**

---

## 🎯 Objetivo

Este script monitoriza cambios en directorios del sistema que suelen ser utilizados por malware (como keyloggers) para registrar datos:

- Detecta modificaciones frecuentes en archivos.
- Registra eventos de creación, eliminación y modificación.
- Lanza alertas si un archivo es modificado demasiadas veces en poco tiempo.
- Almacena logs para revisión y análisis posterior.

---

## 📚 Contexto

Este proyecto forma parte de una serie de prácticas personales realizadas tras cursar un máster en ciberseguridad. Se desarrolla como **complemento defensivo al keylogger educativo** que fue previamente construido como parte de un ejercicio de seguridad ofensiva, también disponible en este mismo repositorio.

---

## ⚙️ Características actuales

- Monitorización de archivos en rutas críticas (`AppData`, `Temp`, `Documents`, `ProgramData`, etc.).
- Alerta visual mediante popup (Windows) si se detecta comportamiento anómalo.
- Registro en archivos `.txt` por tipo de evento (`created.txt`, `modified.txt`, `deleted.txt`, `alert.txt`).
- Umbral configurable de modificaciones por tiempo (`MOD_THRESHOLD` / `MOD_WINDOW`).

---

## 🧠 Roadmap

Próximas mejoras previstas:

- [ ] Integración con `psutil` para detectar procesos sospechosos en ejecución.
- [ ] Asociar eventos de archivos a procesos específicos.
- [ ] Añadir detección de procesos ocultos o sin interfaz de usuario.
- [ ] Correlación entre proceso activo + escritura continua → alerta más precisa.
- [ ] Soporte multiplataforma (Linux/macOS).

---

## 🛠️ Requisitos

- Python 3.10+
- Librerías:
  - `watchdog`
  - (`psutil` próximamente)

```bash
pip install watchdog
```

---

## 📁 Estructura del repositorio

📁 keylogger-defender

 ┣ 📜 monitor.py             # Script principal (este proyecto)
 
 ┣ 📄 created.txt            # Eventos de creación
 
 ┣ 📄 modified.txt           # Eventos de modificación
 
 ┣ 📄 deleted.txt            # Eventos de eliminación
 
 ┣ 📄 alert.txt              # Eventos considerados sospechosos
 
 ┣ 📄 README.md              # Este documento
 
 ┣ 📄 .gitignore


---

## 👨‍💻 Autor

Víctor Barroso

GitHub: @muddysec

---

## 🔒 Ética y uso responsable

Este proyecto ha sido creado con el único propósito de aprender y practicar técnicas de detección defensiva en ciberseguridad. Cualquier uso fuera de entornos controlados, sin consentimiento expreso, es totalmente inadecuado, ilegal y contrario a la intención del autor.
