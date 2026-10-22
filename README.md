# Web Club de Abasto al Mayoreo - Página "En Construcción"

Sitio web temporal de **"En Construcción"** para **Club de Abasto al Mayoreo**, diseñado para desplegarse fácilmente en **Cloudflare Workers** (o Cloudflare Pages).

Basado en la identidad visual oficial de [clubdeabastoalmayoreo.com.mx](https://clubdeabastoalmayoreo.com.mx/), incluyendo:
- Logotipo oficial en alta resolución y favicon.
- Fotografía de la tienda física y centros de distribución.
- Paleta de colores oficial (Naranja `#f05a0a`, Azul Marino `#0e1e38` y neutros).
- Tipografías oficiales de Google Fonts (*Barlow Condensed* y *DM Sans*).
- 4 Pilares del modelo de negocio (Ecosistema productivo, Modelo recurrente, Estructura fiduciaria, Respaldo operativo).
- **Botón directo de WhatsApp** con enlace directo al número `+52 1 998 842 1657` y mensaje predeterminado.
- Enlaces a redes sociales oficiales (Instagram y Facebook).

---

## 📱 Botón de WhatsApp Integrado

- **Teléfono configurado:** `+52 1 998 842 1657` (`5219988421657`)
- **Mensaje predeterminado:**
  > *"¡Hola! Me gustaría solicitar información sobre el Club de Abasto al Mayoreo."*
- **Enlace directo:**
  `https://wa.me/5219988421657?text=¡Hola!%20Me%20gustar%C3%ADa%20solicitar%20informaci%C3%B3n%20sobre%20el%20Club%20de%20Abasto%20al%20Mayoreo.`

---

## 📁 Estructura del Repositorio

```text
.
├── assets/                          # Imágenes y recursos estáticos
│   ├── favicon.png
│   ├── logo-club-de-abasto.webp
│   └── tienda.jpg
├── public/                          # Carpeta para Cloudflare Workers Static Assets o Cloudflare Pages
│   ├── assets/
│   └── index.html
├── src/
│   └── index.js                     # Worker script (sirve archivos o responde HTML autónomo)
├── index.html                       # Página HTML autónoma en la raíz
├── package.json                     # Scripts de desarrollo y despliegue
├── wrangler.toml                    # Configuración de Cloudflare Workers
└── README.md
```

---

## 🚀 Despliegue en Cloudflare

Este repositorio está preparado para funcionar de inmediato mediante **cualquiera** de las siguientes opciones:

### Opción 1: Conectar Repositorio Git desde el Dashboard de Cloudflare (Recomendado)

1. En el panel de [Cloudflare Dashboard](https://dash.cloudflare.com/):
   - Ve a **Workers & Pages** > **Create application**.
2. **Si usas Cloudflare Workers (con Git Integration):**
   - Conecta tu repositorio de GitHub `boscotron/web-clubdeabastoalmayoreo`.
   - Cloudflare detectará automáticamente `wrangler.toml` y desplegará el Worker con la carpeta `./public` como activos estáticos.
3. **Si usas Cloudflare Pages:**
   - Selecciona **Pages** > **Connect to Git**.
   - Directorio de salida / Build output directory: `public` (o dejar vacío para usar la raíz).
   - Comando de compilación: (dejar vacío).
   - Haz clic en **Save and Deploy**.

---

### Opción 2: Despliegue mediante CLI con Wrangler

Si prefieres desplegar directamente desde tu terminal:

```bash
# Instalar dependencias (incluye wrangler)
npm install

# Probar localmente
npm run dev

# Desplegar a tu cuenta de Cloudflare
npm run deploy
```

---

## 🎨 Personalización

Para modificar los textos o el mensaje de WhatsApp:
1. Edita `index.html`.
2. Ejecuta `npm run build` para sincronizar `public/index.html` y `src/index.js` automáticamente.
3. Haz `git commit` y `git push` a tu rama principal en GitHub para que Cloudflare actualice el sitio.
