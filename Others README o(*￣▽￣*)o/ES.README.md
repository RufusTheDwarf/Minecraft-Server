# ⛏️ Servidor Minecraft Gratuito - GitHub Codespaces

> **Cero euros. Cero instalación. Cero complicaciones.**  
> Un servidor Minecraft potente en la nube, listo en menos de una hora.

[![Minecraft](https://img.shields.io/badge/Minecraft-1.21.4+-00AA00?style=flat-square&logo=minecraft&logoColor=white)](https://www.minecraft.net)
[![Java](https://img.shields.io/badge/Java-21-ED8B00?style=flat-square&logo=openjdk&logoColor=white)](https://adoptium.net/)
[![PaperMC](https://img.shields.io/badge/Servidor-PaperMC-0069C0?style=flat-square)](https://papermc.io)
[![Crafty](https://img.shields.io/badge/Panel-Crafty_Controller-F26522?style=flat-square)](https://craftycontrol.com)
[![Playit.gg](https://img.shields.io/badge/Túnel-Playit.gg-7B2FBE?style=flat-square)](https://playit.gg)
[![Licencia MIT](https://img.shields.io/badge/Licencia-MIT-green?style=flat-square)](LICENSE)

---

## 🗺️ Vista general

Este repositorio es una **guía completa, paso a paso y totalmente verificada** para alojar tu propio servidor Minecraft **gratis** en GitHub Codespaces.

Tú y tus amigos podéis jugar juntos en un servidor de alto rendimiento, accesible desde cualquier parte del mundo **sin gastar ni un céntimo**, respetando los límites gratuitos de GitHub.

    Navegador web → GitHub Codespace (Linux) → PaperMC → Playit.gg → Tus amigos 🎮

**Qué obtienes:**
- 🖥️ **Máquina virtual Linux** en la nube (2 núcleos, 8 GB RAM, 32 GB almacenamiento)
- 🟢 **PaperMC** - el servidor Minecraft más optimizado y estable del mercado
- 🧭 **Crafty Controller** - panel web para gestionar el servidor con pocos clics
- 🌐 **Playit.gg** - túnel público para que tus amigos se conecten sin configuración de red
- 💾 **Copias de seguridad automáticas** y **script anti‑suspensión** incluidos

---

## 🎯 ¿Para quién es?

**Para todo el mundo.** Esta guía está redactada de forma didáctica y tranquilizadora.

| Tu perfil | ¿Te sirve esta guía? |
|---|---|
| Principiante total, nunca has tocado Linux | ✅ Sí - todo está explicado y justificado |
| Te manejas en la terminal | ✅ Sí - ve directo a lo esencial |
| Sin experiencia en redes o administración | ✅ Sí - Playit.gg se encarga por ti |
| Sin presupuesto | ✅ Sí - 100 % gratis dentro de los límites |

> Si sabes **copiar y pegar** y **seguir instrucciones**, puedes crear este servidor.

---

## ⚡ Requisitos previos

Solo necesitas:

- [ ] Un **navegador web** (Chrome, Firefox, Edge…)
- [ ] Una **cuenta de GitHub** gratuita - [crear cuenta aquí](https://github.com/signup)
- [ ] Una **cuenta de Playit.gg** gratuita - [crear cuenta aquí](https://playit.gg)

**Ningún software que instalar en tu máquina.**

---

## 📂 Archivos del repositorio (Próximamente)

⚠️ Esta sección está en construcción.  
La información siguiente es solo una previsión.  
Consulta la guía en la carpeta [`Docs`](../Docs).

| Archivo | Función |
|---|---|
| `README.md` | Este archivo - vista general del proyecto |
| `GUIDE.md` | 📘 **La guía completa**, paso a paso |
| `start.sh` | Inicia el servidor con las optimizaciones Aikar’s Flags |
| `keep-alive.sh` | Evita que el Codespace se suspenda automáticamente |
| `backup.sh` | Copia de seguridad automática del mundo Minecraft |

---

## 🚀 Inicio rápido (Próximamente)

⚠️ Esta sección está en construcción.  
La información siguiente es solo una previsión.  
Consulta la guía en la carpeta [`Docs`](../Docs).

    # 1. Clona este repositorio en un Codespace de GitHub
    # 2. Instala Java 21
    sudo apt-get install -y openjdk-21-jdk

    # 3. Inicia el servidor
    bash start.sh

    # 4. Inicia el túnel Playit.gg (en una segunda terminal)
    ./playit

    # 5. Abre Crafty Controller en el puerto 8443

> **Para la guía detallada, consulta [`ES_GUIDE.md`](../Docs/ES_Guide.md).**

---

## 🗂️ Contenido de la guía

El archivo `ES_GUIDE.md` cubre los 17 pasos siguientes:

1. Introducción y material necesario
2. Entender las herramientas (Codespaces, PaperMC, Crafty, Playit.gg)
3. Crear las cuentas de GitHub y Playit.gg
4. Crear el repositorio y el Codespace
5. Familiarizarse con la terminal Linux
6. Instalar Java 21
7. Instalar Python 3 y pip
8. Descargar y configurar PaperMC
9. Configurar Playit.gg
10. Instalar Crafty Controller
11. Añadir el servidor a Crafty
12. Script anti‑suspensión (keep‑alive)
13. Copias de seguridad automáticas
14. ✅ Lista de verificación para iniciar la sesión
15. 🛑 Lista de verificación para detener la sesión
16. Solución de problemas y soporte
17. Seguimiento de la cuota mensual

Cada paso incluye: la explicación del *por qué*, los comandos exactos para copiar y una verificación para asegurar que todo funciona.

---

## ⚠️ Limitaciones y uso responsable

### Cuota gratuita de GitHub Codespaces

    120 horas‑núcleo / mes  →  60 horas de juego en una máquina de 2 núcleos

| Hacer | Evitar |
|---|---|
| ✅ Detener el Codespace tras cada sesión | ❌ Dejarlo funcionando 24/7 |
| ✅ Revisar Settings › Billing & plans | ❌ Ignorar el consumo |
| ✅ Usarlo para sesiones puntuales | ❌ Uso continuo en producción |

> ⚠️ Mantener un servidor de juegos funcionando continuamente **no es conforme** con los términos de uso de GitHub Codespaces. Esta guía está pensada para un uso puntual y responsable.

### Almacenamiento
- **32 GB** disponibles en la máquina de 2 núcleos
- Los datos **no versionados** se pierden si el Codespace se elimina
- Utiliza `backup.sh` y haz commit de tus copias de seguridad regularmente

---

## 🤝 Contribuir

Esta guía se mantiene con cuidado, pero los errores ocurren. ¿Has visto una errata, un comando obsoleto o algo que mejorar?

1. **Abre una [Issue](../../../issues)** para informar del problema
2. **Envía una [Pull Request](../../../pulls)** con tus correcciones

---

## 💬 Soporte y comunidad

| Recurso | Para |
|---|---|
| [Discord PaperMC](https://discord.gg/papermc) | Preguntas sobre el servidor Minecraft |
| [Discord Playit.gg](https://discord.gg/playit) | Problemas de túnel / red |
| [Stack Overflow](https://stackoverflow.com) | Errores Linux / Java con etiquetas `[minecraft]` `[github-codespaces]` |
| [Issues GitHub](../../issues) | Problemas específicos de esta guía |

---

## 📄 Licencia

Distribuido bajo la licencia **MIT**. Libre para usar, modificar y redistribuir conservando el aviso de copyright.

---

<div align="center">

**¿Listo para jugar?**

### 👉 [Abrir la guía completa - ES_Guide.md](Tutorial/🇪🇸Es_Guide.md)

*Gracias a las comunidades PaperMC, Crafty Controller, Playit.gg y GitHub.*

</div>
