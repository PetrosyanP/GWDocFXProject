# Пайплайн подготовки к билду под Сторы

## Steam:

1. Переводим сборку под платформу “PC, Mac & Linux Standalone”.

2. Добавляем ассет “Steamworks.NET” (https://github.com/rlabrecque/Steamworks.NET/releases)

3. В файле steam_appid.txt который в корне проекта поменять AppId на id своего приложения.
Для каждого тренажера свои 2 id (Free, Premium ) записать в ScriptableObject брать из в SteamWorks 
![Alt text](./Images/PreparingAssemblyForTheStore1.png)

4. (только если ассет добавляли заново) Перезапускаем Юнити

5. На DontDestroyObject добавляем скрипт “SteamManager” (в данный момент он висит на объекте “TimeChecker”) 

6. Добавляем ассет “SDK Steamworks”  (https://partner.steamgames.com/downloads/steamworks_sdk.zip)

7. (только если ассет добавляли заново) Перезапускаем Юнити

8. Добавляем ассет "SteamVR Plugin" (https://assetstore.unity.com/packages/tools/integration/steamvr-plugin-32647)

9. Меняем “MessageControllerPlug” на объекте “TimeChecker” на версию под Steam.

10. Убираем настройку роста в сцене обучения и главном меню.

11. В зависимости от версии Free или Premium:

11.1. В скрипте “MessageControllerPlug” меняем переменную “_liceneType” на Free/Premium.

11.2. В префабе UI меняем ссылку в SelectModePanel на SelectModeFree или SelectMode 

12. Проверяем чтобы в ProjectSettings>XR Plug-in Management в Сборках под PC был активен только OpenVR Loader. 

13. Проверяем чтобы в Preferences>VIU Settings был активен только OpenVR. 

14. Проверяем что все настройки плагинов применены(обычно это происходит при смены платформы сборки и включения  OpenVR Loader и OpenVR) Если они будут сразу в проекте и переключать мы их будем системно то я хочу сделать таблицу какие параметры они меняют и в жесткую через код их на всякий случай применять.

15. Создаем билд под PC в папке “OpenVRZamknutoeProstranstvo” или “OpenVRZamknutoeProstranstvoFree” в зависимости от версии приложения.

16. Запаковываем это всё в Zip архив с произвольным именем.

## Oculus: 

1. Добавить в проект ассет “Oculus Integration” только папку Platform (https://assetstore.unity.com/packages/tools/integration/oculus-integration-82022)

2. (только если ассет добавляли заново) Перезапускаем Юнити

3. Меняем “MessageControllerPlug” на объекте “TimeChecker” на версию под Oculus и заполняем поле "appID" в зависимости от приложения для билда(данныи можно получить с страницы приложения в сторе или из заполненого под  сторы специального скриптабл обжекта).

4. Проверяем чтобы в ProjectSettings>XR Plug-in Management в Сборках под Android был активен только Oculus . 

5. Проверяем чтобы в Preferences>VIU Settings был активен Oculus Android. 

6. Проверяем что все настройки плагинов применены(обычно это происходит при смены платформы сборки и включения  Oculus и Oculus Android) Если они будут сразу в проекте и переключать мы их будем системно то я хочу сделать таблицу какие параметры они меняют и в жесткую через код их на всякий случай применять.

7. В сцене обучения меняем модель контроллеров и картинку с контроллерами под Oculus. Так же выключаем картинки одевания и настройки шлема воовсем.

8. В UI меняем  картинку в ControllerInfo под Oculus.

7. Добавляем в ProjectSettings>Player>PublishingSettings ключ подписи и вводим логин пароли от ключа и проекта.

8. Меняем версию в шапке ProjectSettings>Player  на большую и Bundle version.

9. Меняем файл манифеста под Oculus.

10. В зависимости от версии Free или Premium:

10.1. В скрипте “MessageControllerPlug” меняем переменную “_liceneType” на Free/Premium.

10.2. В префабе UI меняем ссылку в SelectModePanel на SelectModeFree или SelectMode 

11. Проверяем что в ProjectSettings>Player>PublishingSettings стоит галочка у Custom Main Manifest.

12. Устанавливаем имя проекта “VRTrainersConfinedSpace” а компанию “Goldfinchworks” .

13. Создаем билд под Android.

## VivePort:

1. Устанавливаем плагин “VIVEPORT SDK” (https://developer.vive.com/resources/viveport/viveport-documentation/english/viveport-sdk/integration-viveport-sdk/unity-developers/)

2. (только если ассет добавляли заново) Перезапускаем Юнити

3. На DontDestroyObject добавляем скрипт “MainThreadDispatcher” (в данный момент он висит на объекте “TimeChecker”).

4. Меняем “MessageControllerPlug” на объекте “TimeChecker” на версию под Vive заполняем поле "appID" и "apiKey" в зависимости от приложения для билда(данныи можно получить с страницы приложения в сторе или из заполненого под  сторы специального скриптабл обжекта).

5. Проверяем чтобы в ProjectSettings>XR Plug-in Management в Сборках под Android был активен только WaveXR . 

6. Проверяем чтобы в Preferences>VIU Settings был активен WaveVR. 

7. Проверяем что все настройки плагинов применены(обычно это происходит при смены платформы сборки и включения  WaveXR и WaveVR) Если они будут сразу в проекте и переключать мы их будем системно то я хочу сделать таблицу какие параметры они меняют и в жесткую через код их на всякий случай применять.

8. Добавляем в ProjectSettings>Player>PublishingSettings ключ подписи и вводим логин пароли от ключа и проекта.

9. Меняем версию в шапке ProjectSettings>Player  на большую.

10. В зависимости от версии Free или Premium:

10.1. В скрипте “MessageControllerPlug” меняем переменную “_liceneType” на Free/Premium.

10.2. В префабе UI меняем ссылку в SelectModePanel на SelectModeFree или SelectMode 

11. Устанавливаем имя проекта “VRTrainersConfinedSpace” а компанию “Goldfinchworks” .

12. Меняем файл манифеста под Vive.

13. Проверяем что в ProjectSettings>Player>PublishingSettings стоит галочка у Custom Main Manifest.

14. Создаем билд под Android.
