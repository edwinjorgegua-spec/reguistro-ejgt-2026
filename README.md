# S.H.A.S. Educativo 2026 — Registro Pedagógico

App web offline-first para docentes bolivianos con control de acceso, sincronización QR manual y recuperación de datos.

## 🎨 Identidad visual

La app usa los íconos oficiales **Registro Pedagógico Docente Bolivia** en:
- Pantalla de login
- Ícono de la app instalada (Android/iOS/PC)
- Pestaña del navegador (favicon)

Archivos: `icon-192.png` (Android Chrome) y `icon-512.png` (iOS, Windows, alta resolución).

## 🔐 Sistema de Control de Acceso

### Para TI (admin)
Eres el **único** que puede generar códigos de acceso. Para activar el modo admin:

1. Abre la app → verás la pantalla de login con el ícono Bolivia
2. Toca **"⚙️ Modo Admin"**
3. Ingresa la contraseña: **`EDWIN2026`** (cámbiala al primer uso)
4. Entra al panel admin desde el menú lateral

### Generar códigos para otros docentes
En el panel admin puedes:
- ➕ Generar código nuevo (formato `XXXX-XXXX-XXXX-XXXX`)
- 📋 Copiar código al portapapeles
- 💬 Compartir por WhatsApp directamente
- 🔳 Mostrar QR para que lo escaneen
- 📥 Exportar lista de códigos como CSV
- 🚫 Revocar códigos ya entregados

### Para otros usuarios
Reciben tu código y lo ingresan en la pantalla de login de su copia descargada.

## 🔄 Sincronización Manual (sin internet)

La app **NO** sincroniza automáticamente. Solo cuando presionas un botón:

### Opción 1: Archivo .shas2026 (PC ↔ Móvil)
- Pestaña **Sincronizar → Exportar Backup**
- Envíalo por WhatsApp/Drive/USB a tu otro dispositivo
- En el otro dispositivo → **Importar datos**

### Opción 2: QR Code (datos pequeños, sin red)
- Pestaña **Sincronizar → Mostrar datos como QR**
- En el otro dispositivo → **Escanear QR (cámara)**

## 🔓 Recuperación si pierdes el celular

Al primer uso, la app genera **6 palabras de recuperación** (ej: `canela-sol-rio-nieve-perro-mar`).

**IMPORTANTE:**
1. Anota estas palabras en papel y guárdalas en lugar seguro
2. Haz backups regulares con **Exportar Backup** (.shas2026)
3. La app te recordará hacerlo cada 7 días

**Si pierdes el celular:**
1. Instala la app en nuevo dispositivo
2. En pantalla de login → **🔐 Recuperar datos**
3. Ingresa tus 6 palabras + carga tu archivo `.shas2026`
4. Tus datos se restauran completamente

## 🚀 Deploy en Netlify

### Opción A: Drag & Drop (30 segundos)

1. Ve a [app.netlify.com/drop](https://app.netlify.com/drop)
2. Arrastra la **carpeta completa descomprimida** (con TODOS los archivos: HTML + 2 PNGs + _headers + _redirects)
3. Obtendrás una URL `https://xxx.netlify.app`

⚠️ **IMPORTANTE**: Asegúrate que `icon-192.png` e `icon-512.png` estén en la raíz junto a `index.html` — Netlify los servirá como recursos estáticos.

### Opción B: Desde GitHub

1. Crea un repo y sube todos los archivos
2. Netlify: **Add new site → Import from Git**
3. Auto-deploy en cada push

## 📁 Archivos del paquete

| Archivo | Tamaño | Propósito |
|---------|-------:|-----------|
| `index.html` | 261 KB | App completa |
| `icon-192.png` | 126 KB | Ícono Android Chrome |
| `icon-512.png` | 152 KB | Ícono iOS / alta resolución |
| `_headers` | 0.8 KB | Headers de seguridad + caché PNG |
| `_redirects` | 0.2 KB | SPA catch-all |
| `netlify.toml` | 0.5 KB | Configuración Netlify |
| `README.md` | 4.5 KB | Este archivo |

## 🔒 Seguridad

- Códigos validados **matemáticamente** con SHA-256 offline (sin servidor)
- Tamper detection: modificar 1 carácter del código lo invalida
- Palabras de recuperación: 48 bits de entropía (281 trillones combinaciones)
- Headers HTTP: `nosniff`, `SAMEORIGIN`, `HSTS`, `Permissions-Policy`
- Iconos PNG con cache de 1 año (`max-age=31536000, immutable`)

## 🧪 Tests ejecutados

- ✅ 37 tests unitarios (códigos, validación, admin, recovery)
- ✅ 24 tests de integración (PDF Illimani → import → notas → save → recover)
- ✅ 1000 códigos generados sin colisiones
- ✅ Todos los recursos sirven correctamente con MIME types correctos
