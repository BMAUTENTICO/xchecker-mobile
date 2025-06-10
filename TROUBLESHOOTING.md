# Guía de Solución de Problemas - xChecker Mobile

## Pasos para Abrir el Proyecto

1. Descomprime xchecker-mobile.zip
2. Abre Android Studio
3. Selecciona File > Open
4. Navega a la carpeta descomprimida
5. Selecciona "OK"
6. Espera a que el proyecto se indexe y sincronice

## Solución de Problemas Comunes

### Error: Gradle sync failed

1. Verifica tu conexión a internet
2. Ve a File > Settings > Build, Execution, Deployment > Gradle
3. Asegúrate que "Gradle JDK" esté configurado (usa JDK 11 o superior)
4. Click en "Try Again" en la barra de error

### Error: SDK no encontrado

1. Ve a Tools > SDK Manager
2. Instala Android SDK 33 (o la versión que necesites)
3. Instala también Android Build Tools
4. Sincroniza el proyecto nuevamente

### Error: R.layout no encontrado

1. Ve a File > Invalidate Caches / Restart
2. Selecciona "Invalidate and Restart"
3. Espera a que Android Studio se reinicie
4. El proyecto se recompilará automáticamente

## Pasos para Generar el APK

### APK de Debug (para pruebas)

1. Ve a Build > Build Bundle(s) / APK(s)
2. Selecciona "Build APK(s)"
3. Espera a que termine la compilación
4. El APK estará en: app/build/outputs/apk/debug/app-debug.apk

### APK de Release (versión final)

1. Ve a Build > Generate Signed Bundle / APK
2. Selecciona "APK"
3. Click en "Next"
4. En "Key store path":
   - Si es la primera vez: Create new
   - Llena los datos:
     * Key store path: selecciona una ubicación
     * Password: crea una contraseña
     * Alias: crea un alias
     * Validity: 25
     * Certificate: llena tus datos
5. Click en "Next"
6. Selecciona "release"
7. Click en "Finish"
8. El APK estará en: app/release/app-release.apk

## Verificación de la Instalación

1. Habilita la "Instalación de orígenes desconocidos" en tu dispositivo Android
2. Copia el APK a tu dispositivo
3. Abre el APK en tu dispositivo
4. Click en "Instalar"

## Requisitos Mínimos

- Android Studio (última versión)
- JDK 11 o superior
- Android SDK 33
- Dispositivo/Emulador con Android 7.0 o superior

## Estructura del Proyecto

```
xchecker-mobile/
├── app/
│   ├── src/main/
│   │   ├── java/com/example/xcheckermobile/
│   │   │   ├── MainActivity.kt
│   │   │   └── SplashActivity.kt
│   │   ├── res/
│   │   │   ├── layout/
│   │   │   │   ├── activity_main.xml
│   │   │   │   └── activity_splash.xml
│   │   │   └── values/
│   │   │       ├── colors.xml
│   │   │       └── themes.xml
│   │   └── AndroidManifest.xml
│   └── build.gradle
├── build.gradle
└── settings.gradle
```

## Contacto y Soporte

Si encuentras algún problema no cubierto en esta guía, por favor:

1. Verifica que todos los archivos estén en su lugar correcto
2. Asegúrate de tener todas las dependencias instaladas
3. Revisa los logs de error en Android Studio (View > Tool Windows > Logcat)

## Notas Importantes

- La aplicación requiere permisos de Internet
- Asegúrate de tener suficiente espacio en disco
- Mantén Android Studio actualizado
- Usa siempre la última versión de Gradle
