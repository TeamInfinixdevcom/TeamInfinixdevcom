# Kolbi Monitor Web

Aplicación web para monitoreo, métricas y gestión operativa del sistema **Kolbi Monitor**.

## Funcionalidades

- Dashboard / inicio con resumen general
- Gráficas y tendencias
- Métricas avanzadas
- Manejo de solicitudes
- Inventario

---

## Capturas (Monitor Web)

> Nota: para que GitHub muestre las imágenes, se usan links directos `i.imgur.com`.

### Inicio
![Inicio](https://i.imgur.com/eaYlQXi.png)

### Gráficas
![Gráficas](https://i.imgur.com/f7IpieR.png)

### Métricas avanzadas
![Métricas avanzadas](https://i.imgur.com/m1HF1KX.png)

### Manejo de solicitudes
![Manejo de solicitudes](https://i.imgur.com/YOQqsgy.png)

### Inventario
![Inventario](https://i.imgur.com/EuC4s0K.png)

### Presentación
![Presentación](https://i.imgur.com/YOQk8EY.png)

---

## Requisitos

- Node.js (recomendado: LTS)
- npm
- Proyecto configurado en Firebase (Auth/Firestore/Hosting según aplique)

---

## Instalación y ejecución

Instalar dependencias:

```bash
npm install
```

Ejecutar en desarrollo:

```bash
npm start
```

Compilar para producción:

```bash
npm run build
```

Tests (si están configurados):

```bash
npm test
```

---

## Variables de entorno

Crea un archivo `.env` (no se sube al repositorio) para credenciales/URLs del proyecto.

Ejemplo (ajusta según tu configuración):

```bash
REACT_APP_FIREBASE_API_KEY=...
REACT_APP_FIREBASE_AUTH_DOMAIN=...
REACT_APP_FIREBASE_PROJECT_ID=...
```

---

## Asignar permisos de admin en Firebase (Custom Claims)

Para que un usuario pueda cargar inventario u operar funciones restringidas, debe tener el claim `admin` en **Firebase Auth**.

### Uso

1. Obtén el UID del usuario en Firebase Console → Authentication.
2. Descarga la **Service Account Key** desde Firebase Console → Project Settings → Service accounts.
3. Ejecuta:

```bash
node scripts/cambiodeposicionaADMIN.js <ruta_al_serviceAccountKey.json> <UID_DEL_USUARIO>
```

Ejemplo:

```bash
node scripts/cambiodeposicionaADMIN.js "./serviceAccountKey.json" "GDSTAxaKsRbQNnW3IjpYeIsIzSz2"
```

4. El usuario debe cerrar sesión y volver a iniciar para que el claim se aplique.

### Seguridad

- Nunca subas `serviceAccountKey.json` al repositorio.
- Guárdalo localmente y agrégalo a `.gitignore` si hace falta.
