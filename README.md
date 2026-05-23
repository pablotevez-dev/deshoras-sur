# 💚 Deshoras Sur — Sitio web y herramientas digitales

> ONG de jóvenes comprometidos con la promoción de la igualdad de oportunidades para personas en situación de vulnerabilidad. Lomas de Zamora, Buenos Aires.

🌐 **Sitio:** [pablotevez-dev.github.io/deshoras-sur](https://pablotevez-dev.github.io/deshoras-sur)

---

## ¿Qué hay en este repositorio?

Esta carpeta `git/` contiene las páginas estáticas que GitHub Pages publica:

| Archivo | Descripción | URL |
|---|---|---|
| `index.html` | Linktree — Botonera principal con todos los accesos | `/deshoras-sur` |
| `recursero.html` | Recursero 2026 — asistencia alimentaria, duchas y servicios por día | `/deshoras-sur/recursero.html` |

Las herramientas que requieren backend (formularios, lectura/escritura en Google Sheets) viven en `../AppScrip/` y se publican como **web apps de Google Apps Script**. La Botonera linkea directo a sus URLs `/exec`.

---

## Herramientas

### 🗺 Recursero 2026
Guía de recursos para personas en situación de calle en Lomas de Zamora y alrededores. Incluye:
- Asistencia alimentaria organizada por día de la semana
- Lugares y horarios de duchas
- Servicios sociales y talleres (Centro Barrial Codo a Codo, Dirección de Organización Comunitaria)

### 📋 Relevamiento
Formulario web para registrar a las personas que vemos en cada recorrida (nombre, DNI, hijos, ubicación, trabajo, asistencia social). Backend en Apps Script, datos en Google Sheet.

### 👕 Registrar pedido
Formulario mobile-first para cargar pedidos de ropa. Flujo en 4 pasos: recorrido (*Barrera* / *Laprida*) → voluntario → personas con sus ítems → resumen. Cada ítem tiene una **cascada Categoría → Ítem** (las categorías y sus ítems se leen de hojas separadas en el Sheet, así se actualizan sin tocar código). Genera un texto listo para compartir por WhatsApp.

### 📦 Gestionar pedido
Misma URL del Apps Script de pedidos con `?page=entregas`. Tres solapas:
- **Pendientes** — toma de pedidos que nadie agarró todavía.
- **Mis pedidos** — marca como entregado lo que ya tomaste.
- **❄️ Invierno** — inventario propio para la campaña de invierno (ver abajo).

Cada ítem del pedido se toma de forma independiente. Confirmación previa por modal para evitar tomas accidentales.

### ❄️ Campaña de Invierno
Vive como tercera solapa dentro de "Tomar un pedido". Cada voluntario carga **cuántos artículos de invierno tiene guardados en su casa** (Manta, Frazada, Gorro, Bufanda, Guante, Cuellito). Los cambios se guardan solos con cada `+`/`−` (autosave con debounce). Al ver el total general en el Sheet se sabe con cuánto stock cuenta la ONG sin tener que preguntar uno por uno.

La lista de artículos sale de la hoja `ArticuloInvierno` y los datos se guardan en `Campaña Invierno` (Voluntario · Articulo · Cantidad · Actualizado). Si la cantidad vuelve a 0, la fila se elimina sola para mantener la hoja limpia.

### 🧺 Stock de Cocina
Tablero que muestra qué alimentos y artículos de papelería hay que ir comprando, clasificados por urgencia (`Pedir urgente` / `Sin stock` / `Ir juntando` para alimentos).

### 💡 Enviar una propuesta
Link `mailto:` precargado a la Comisión Directiva (`comision.directiva@deshorassur.org.ar`) con asunto y cuerpo armados para que cualquier voluntario pueda proponer un proyecto.

### 🔗 Botonera (linktree)
Página central de acceso a todas las herramientas + enlaces a Instagram, WhatsApp y sitio web institucional.

> **Patrón compartido**: todas las pantallas internas tienen un footer **"← Volver a la Botonera"** que lleva al linktree.

---

## Cómo actualizar el Recursero

Si cambian horarios u organizaciones, editá directamente `recursero.html` desde GitHub:

1. Abrí el archivo `recursero.html` en el repositorio
2. Hacé clic en el **lápiz ✏️** (arriba a la derecha)
3. Buscá la organización o el día que querés modificar
4. Editá el texto
5. Clic en **"Commit changes"**

El sitio se actualiza solo en 1-2 minutos.

---

## Cómo actualizar las web apps de Apps Script

Para Pedidos, Relevamiento o Cocina:

1. Abrí el proyecto Apps Script desde [script.google.com](https://script.google.com) (o desde el Sheet asociado → **Extensiones → Apps Script**).
2. Pegá el contenido actualizado en el `.gs` o `.html` correspondiente.
3. **Deploy → Manage deployments → ✏️ → Version: `New version` → Deploy**.

> ⚠️ Si dejás el dropdown en `Active` en vez de `New version`, la URL `/exec` sigue sirviendo la versión anterior aunque diga "Deployed". Es el error más común.

La URL `/exec` no cambia con cada redeploy, así que los links de la Botonera se mantienen.

---

## Contacto

- 📧 ongdeshorassur@gmail.com
- 📱 +54 9 11 7067-8158
- 📸 [@deshorassur](https://www.instagram.com/deshorassur)
- 🌐 [ongdeshorassur.wixsite.com/deshoras-sur](https://ongdeshorassur.wixsite.com/deshoras-sur)

---

*Hecho con 💚 por y para Deshoras Sur · 2026*
