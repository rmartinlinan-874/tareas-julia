# Tareas de Julia — puesta en marcha

Esta app es independiente de la de Irene: necesita su **propio proyecto
de Firebase** y su **propio hosting** (otro repo de GitHub Pages, o una
carpeta distinta en el mismo repo con su propia URL).

## 1. Crear el proyecto de Firebase

1. Ve a https://console.firebase.google.com y crea un proyecto nuevo,
   por ejemplo `tareas-julia`.
2. Dentro del proyecto: **Compilación → Realtime Database → Crear base
   de datos**. Elige una ubicación en Europa (`europe-west1`).
3. En la pestaña **Reglas**, sustitúyelas por:
   ```json
   {
     "rules": {
       ".read": true,
       ".write": true
     }
   }
   ```
   (Sin esto, la app no podrá leer ni guardar nada — por defecto
   Firebase bloquea todo.)
4. En **Configuración del proyecto → Tus apps**, añade una app web
   (icono `</>`). Te dará un bloque `firebaseConfig` con 7 valores.
5. Copia esos 7 valores dentro de `index.html`, en el bloque
   `window.FIREBASE_CONFIG` (sustituyendo los `PEGA_AQUI...`).

## 2. Subir los archivos

Sube `index.html`, `manifest.json`, `favicon-32.png` y
`apple-touch-icon.png` a un repositorio de GitHub y activa GitHub
Pages (Settings → Pages → rama y carpeta donde están estos archivos).

Los dos iconos (`favicon-32.png` y `apple-touch-icon.png`) se generan
a partir de la foto de Julia — en cuanto la compartas te los preparo
recortados al tamaño correcto.

## 3. Añadir el acceso directo al móvil

- **Android**: abre la URL en Chrome → menú (⋮) → "Añadir a pantalla
  de inicio".
- **iPhone**: abre la URL en Safari → compartir → "Añadir a pantalla
  de inicio".

## Notas

- No hay modo padre ni PIN: cualquiera que tenga el móvil abierto
  puede marcar las tareas directamente.
- Los datos se guardan en Firebase Realtime Database, así que se
  sincronizan al instante entre el móvil tuyo y el de la madre de
  Julia si ambos abrís la misma URL.
