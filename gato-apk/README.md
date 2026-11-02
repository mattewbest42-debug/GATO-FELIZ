# Mi Gato · App Android (APK)

App para controlar las comidas de tu gato. Esta carpeta ya está preparada para convertirse en un APK con Capacitor.

## Opción A (la más fácil): GitHub crea el APK por ti

No necesitas instalar nada en tu computadora.

1. Crea un repositorio nuevo en GitHub.
2. Sube **todo el contenido** de esta carpeta (incluida la carpeta oculta `.github`).
3. Ve a la pestaña **Actions** del repositorio. Verás el trabajo **Crear APK** corriendo (tarda unos 5 minutos).
4. Cuando termine en verde, ábrelo y descarga **mi-gato-apk** en la sección *Artifacts*. Dentro del zip está `app-debug.apk`.
5. Pásalo a tu celular e instálalo. Android te pedirá permitir instalar apps de origen desconocido.

Si cambias algo en `www/index.html` y haces un nuevo `push`, GitHub crea un APK actualizado.

## Opción B: compilarlo en tu computadora

Necesitas Node.js 20, Java 17 y Android Studio.

```bash
npm install
npx cap add android
npx cap sync android
cd android
./gradlew assembleDebug
```

El APK queda en `android/app/build/outputs/apk/debug/app-debug.apk`.

## Estructura

- `www/index.html`: la app completa (diseño y código).
- `capacitor.config.json`: nombre de la app (`Mi Gato`) e identificador (`com.migato.app`).
- `.github/workflows/build-apk.yml`: receta para que GitHub compile el APK.

## Notas

- El APK es de depuración: sirve para instalar en tu celular. Para publicarlo en Google Play se necesita un APK/AAB firmado.
- Los datos del gato se guardan en el celular donde está instalada la app.
