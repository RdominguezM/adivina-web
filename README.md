# Adivina el Personaje

Juego web multijugador para adivinar personajes con amigos. Se publica gratis en GitHub Pages y usa Firebase (plan gratuito Spark) para sincronizar las partidas en tiempo real.

## Archivos

- `index.html`: el juego completo.
- `firestore.rules`: reglas de seguridad de la base de datos.

## 1. Crear el proyecto en Firebase

1. Entra a https://console.firebase.google.com y crea un proyecto. Google Analytics es opcional; puedes desactivarlo.
2. **Authentication** > Comenzar > pestaña **Sign-in method** > activa **Anónimo** (Anonymous) y guarda.
3. **Firestore Database** > Crear base de datos > elige una ubicación cercana (por ejemplo `us-east1`) > modo producción.
4. En Firestore, pestaña **Reglas**: borra lo que haya, pega el contenido de `firestore.rules` y haz clic en **Publicar**.
5. **Configuración del proyecto** (ícono de engrane) > **Tus apps** > ícono web `</>` > registra la app (no marques Firebase Hosting).
6. Copia el objeto `firebaseConfig` que te muestra.

## 2. Pegar la configuración

Abre `index.html`, busca el bloque `FIREBASE_CONFIG` al inicio del script y reemplaza los valores de ejemplo por los de tu proyecto.

## 3. Publicar en GitHub Pages

1. Crea un repositorio público en GitHub (por ejemplo `adivina-el-personaje`).
2. Sube `index.html`, `firestore.rules` y este `README.md` (botón **Add file > Upload files**).
3. En el repositorio: **Settings > Pages** > Source: **Deploy from a branch** > Branch: `main` / carpeta `/ (root)` > **Save**.
4. En uno o dos minutos el juego queda en `https://TU-USUARIO.github.io/adivina-el-personaje/`.

## 4. Autorizar el dominio en Firebase

En Firebase: **Authentication > Configuración (Settings) > Dominios autorizados** > agrega `TU-USUARIO.github.io`.

## Notas

- Tus amigos solo necesitan el link; no necesitan cuenta.
- Cada navegador recibe una identidad anónima. Si alguien cambia de dispositivo o borra los datos del navegador a mitad de partida, entra como un jugador nuevo.
- Plan gratuito de Firebase: alrededor de 50,000 lecturas y 20,000 escrituras por día. Si se superan, Firestore deja de funcionar el resto del mes en el plan gratuito; con partidas entre amigos no deberías acercarte.
- La configuración de Firebase en `index.html` no es secreta. Lo que protege los datos son las reglas de `firestore.rules`.
