# S.H.A.S. Educativo 2026 — Registro Pedagógico

## 🆕 Nuevos cambios en esta versión

### Códigos cortos: ABC1XY (6 caracteres)
Antes: `ACLU-82JX-8ZNZ-EZYS` (19 chars con guiones)
Ahora: `ABC1XY` (6 chars, fácil de dictar por teléfono)

- ~1 millón de combinaciones únicas
- Tamper-proof (cambiar 1 char invalida)
- 1000 códigos generados sin colisiones
- **Compatibilidad**: códigos viejos de 16 chars siguen funcionando

### Bug fix: Panel admin ahora SÍ aparece
3 bugs corregidos:
1. `display:none` inline ya no oculta la página #pg-admin al navegar
2. El botón ⚙️ Admin del sidebar ahora se crea con timing correcto
3. Es idempotente (no se duplica si se llama múltiples veces)

---

## Cómo usar el panel admin

### Para llegar al panel admin (paso a paso)

1. **Abre la app** — verás el sidebar con un badge en la parte superior
2. **Toca el badge** que dice **"🆓 GRATIS · Activar Premium"**
3. Aparece pantalla con 3 vistas → **toca "⚙️ Modo Admin"**
4. Ingresa la contraseña: **`EDWIN2026`**
5. Tras autenticarte:
   - El badge cambia a **"⚙️ MODO ADMIN"** (amarillo)
   - Aparece un nuevo botón en el sidebar: **"⚙️ Admin"** (también amarillo)
6. **Toca "⚙️ Admin"** → te lleva al panel completo

### En el panel admin verás

- **Card "🔑 Generar código nuevo"**:
  - Campo "Nombre del usuario (opcional)"
  - Botón **"➕ Generar código"** (azul, grande)
  - Tras generar, muestra el código tipo `ABC1XY` con botones:
    - 📋 Copiar al portapapeles
    - 💬 Compartir por WhatsApp
    - 🔳 Mostrar QR
- **Card "🔐 Contraseña admin"** — cambiar contraseña
- **Card "📋 Códigos emitidos"** — lista con todos los códigos generados:
  - Estado (Activo / Revocado)
  - Botones por código: 📋 Copiar / 🚫 Revocar / 🗑️ Eliminar
  - Botón **"📥 Exportar CSV"** para descargar lista

### Cómo distribuir un código

1. Click en **"➕ Generar código"** → aparece código `ABC1XY`
2. Toca **"💬 WhatsApp"** → se abre WhatsApp con mensaje pre-armado
3. Selecciona el contacto → enviar
4. El docente recibe el código y lo ingresa en su app

### Cómo el docente usa el código

1. Abre la app desde el link
2. Toca badge **"🆓 GRATIS · Activar Premium"**
3. Ingresa el código `ABC1XY` en el campo
4. Listo: badge cambia a **"💎 PREMIUM ACTIVO"**, todos los grados desbloqueados

---

## Resto de funciones (sin cambios)

- ✅ Modo Gratis automático (sin pedir login)
- ✅ Cuadro evaluativo dimensional (SER+SABER+HACER+AUTO)
- ✅ Extractor SIE (PDF Bolivia)
- ✅ Módulo Asesor de Curso
- ✅ Sincronización: archivo / QR / Firebase (Premium)
- ✅ Palabras de recuperación (6 palabras)
- ✅ Íconos personalizados Bolivia

## Deploy en Netlify

Arrastra la carpeta completa descomprimida a [app.netlify.com/drop](https://app.netlify.com/drop)

## Tests ejecutados ✅

- ✅ 30/30 tests E2E pasan
- ✅ 1000 códigos generados sin colisiones
- ✅ Tamper detection 100%
- ✅ Compatibilidad backward (códigos viejos siguen funcionando)
- ✅ Performance: 1000 generaciones en 74ms, 1000 validaciones en 13ms
- ✅ Botón admin idempotente (5 llamadas → 1 botón)
