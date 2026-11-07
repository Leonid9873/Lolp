# Укради яйцо (Android)

3D-игра на Three.js в оболочке Android WebView. Играть можно без интернета, кроме шрифтов Google Fonts: без сети подставляются системные.

## Как получить APK (без установки Android Studio)

1. Создайте на github.com новый репозиторий и загрузите в него все файлы этой папки, включая скрытую папку `.github`.
   Из терминала:
   ```
   git init
   git add .
   git commit -m "Укради яйцо"
   git branch -M main
   git remote add origin https://github.com/<ваш-логин>/<репозиторий>.git
   git push -u origin main
   ```
2. Откройте вкладку **Actions**. Сборка **Build APK** запустится сама (около 3-5 минут). Если нет, нажмите **Run workflow**.
3. Откройте завершённый запуск и скачайте **steal-the-egg-apk** из раздела Artifacts. Внутри будет `app-debug.apk`.
4. Перенесите файл на телефон и откройте его. Android попросит разрешить установку из неизвестного источника.

## Сборка на своём компьютере

Нужны Android Studio (или JDK 17 и Android SDK 34) и Gradle 8.9.

1. Скачайте https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js и положите файл в `app/src/main/assets/three.min.js`.
2. Выполните `gradle assembleDebug`. APK появится в `app/build/outputs/apk/debug/app-debug.apk`.

## Что внутри

- `app/src/main/assets/index.html` содержит всю игру.
- `app/src/main/java/com/stealtheegg/game/MainActivity.java` задаёт полноэкранный WebView в портретной ориентации.
- `.github/workflows/build-apk.yml` собирает APK на GitHub.

Подпись у APK отладочная. Для публикации в Google Play нужна release-сборка со своим ключом.
