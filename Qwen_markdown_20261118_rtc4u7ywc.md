# AeroVista — APK

## Ottieni l'APK senza installare nulla (consigliato)
1. Carica questa cartella su un repository GitHub (branch `main`).
2. Apri **Actions → Build AeroVista APK → Run workflow**.
3. A build conclusa, scarica l'artifact **AeroVista-APK**.
4. Copia `app-arm64-v8a-release.apk` sul telefono Android e aprilo
   (abilita "Installa app sconosciute" per il tuo file manager).
   In alternativa usa `app-release.apk` (universale, tutte le CPU).

## Build locale
Requisiti: Flutter 3.24.x stable, JDK 17, Android SDK (Android Studio).

- macOS / Linux: `bash tools/build_apk.sh`
- Windows: `tools\build_apk.bat`
- Telefono collegato in USB: `flutter install --release`

Output: `build/app/outputs/flutter-apk/*.apk`

## Note
- L'APK è firmato con la chiave di debug del template Flutter: è installabile
  direttamente, ma non pubblicabile su Play Store. Per una firma tua, crea
  `android/key.properties` e configura `signingConfigs` in `android/app/build.gradle`.
- Nessuna rete disponibile? L'app parte in modalità DEMO con flotta simulata,
  allarmi, export e console completa comunque funzionanti.
- Dati: adsb.fi (primario) e OpenSky Network (fallback), solo uso personale non
  commerciale. Mappe © OpenStreetMap contributors, tiles © CARTO.