# Taller de Liderazgo Grido — puesta en marcha (Firebase + GitHub Pages)

Tiempo estimado: 20 minutos. Necesitás una cuenta de Google y una de GitHub.

## 1. Crear el proyecto en Firebase

1. Entrá a https://console.firebase.google.com y tocá **Crear un proyecto** (por ejemplo, `taller-liderazgo`). Podés desactivar Google Analytics.
2. En el menú **Compilación > Firestore Database** tocá **Crear base de datos**.
   - Ubicación: `southamerica-east1 (São Paulo)`.
   - Modo: **producción**.
3. En **Compilación > Authentication** tocá **Comenzar**, pestaña **Método de acceso**, elegí **Anónimo** y **Habilitar**.

## 2. Pegar las reglas de seguridad

1. Abrí el archivo `firestore.rules` y reemplazá `CAMBIAR_ESTA_CLAVE` por una clave de facilitador que solo vos conozcas.
2. En **Firestore Database > Reglas** borrá lo que haya, pegá el contenido completo del archivo y tocá **Publicar**.

## 3. Conectar la página con tu proyecto

1. En la consola de Firebase: ícono de engranaje **> Configuración del proyecto > Tus apps**, tocá el ícono **Web `</>`**, poné un nombre y **Registrar app**. No hace falta activar Hosting.
2. Copiá los valores de `firebaseConfig` (apiKey, authDomain, projectId, storageBucket, messagingSenderId, appId).
3. Abrí `index.html` con un editor de texto, buscá `window.FIREBASE_CONFIG` y reemplazá cada `PEGAR_...` por tu valor. Guardá.

Los valores de `firebaseConfig` no son secretos: Google los diseñó para ir en páginas públicas. La protección la dan las reglas del paso 2.

## 4. Publicar en GitHub Pages

1. En https://github.com tocá **New repository** (por ejemplo, `taller-liderazgo`), marcalo **Public** y crealo.
2. **Add file > Upload files**, subí `index.html` y tocá **Commit changes**.
3. **Settings > Pages**: en *Branch* elegí `main` y carpeta `/ (root)`, y **Save**.
4. En 1 o 2 minutos aparece el link: `https://TU_USUARIO.github.io/taller-liderazgo/`.
5. En Firebase, **Authentication > Configuración > Dominios autorizados**, agregá `TU_USUARIO.github.io`.

## 5. Usar el taller

- **Participantes:** compartí el link tal cual. No necesitan cuenta; los aportes son anónimos.
- **Facilitador:** abrí el link agregando `#facilitador` al final, escribí la clave del paso 2 y tocá **Entrar**. En ese navegador vas a ver la barra de facilitador (cambiar de fase y **Reiniciar todo de cero**). La próxima vez que abras desde el mismo navegador, entra sola.

## Si algo no funciona

| Mensaje arriba a la derecha | Qué revisar |
|---|---|
| Falta configurar Firebase | Paso 3: quedó algún `PEGAR_...` en `index.html`. |
| No se pudo iniciar sesión anónima | Paso 1.3: activar **Anónimo** en Authentication. |
| Se cortó la conexión | Paso 2: las reglas no están publicadas o tienen un error. |
| “Clave incorrecta” al entrar como facilitador | La clave no coincide con la de `firestore.rules` (respeta mayúsculas). |

El plan gratuito de Firebase (Spark) alcanza de sobra para un curso.
