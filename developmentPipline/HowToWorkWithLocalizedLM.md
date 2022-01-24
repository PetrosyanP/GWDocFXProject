# ПАЙПЛАЙН СОЗДАНИЯ РЕЖИМА ТРЕНАЖЕРА  
(Апдейт после внедрения локализации в тренажеры)  

## 1. Подготовка  
<details>
<summary>Раскрыть</summary>

- Создать ассет LessonManagerErrors ([См. Приложение 1](#приложение-1-работа-с-ассетом-lessonmanagererrors))  
- Прилинковать ассет LessonManagerErrors к LessonManager  
![Прилинковать созданный ассет к LessonManager](../Images/HowToWorkWithLocalizedLM1.png)  
- Создать ассет AudioAdviceSO ([См. Приложение 3](приложение-3-работа-с-ассетом-audioadviceso))  
- Прилинковать созданный ассет к LessonManager  
![Прилинковать ассет AudioAdviceSO к LessonManager](../Images/HowToWorkWithLocalizedLM2.png)

</details>

## 2 Настройка ошибок в LM  
<details>
<summary>Раскрыть</summary>

- Открыть LM (Window-LessonManager_V2)  
- Выбрать режим из выпадающего списка  
![Выбор режима LM](../Images/HowToWorkWithLocalizedLM3.png)  
- Открыть шаг, который необходимо настроить, нажав на кнопку с ID шага  
![Открытие шага](../Images/HowToWorkWithLocalizedLM4.png)  
- Раскрыть блок "Список ивентов, являющихся ошибкой"  
![Блок "Список ивентов, являющихся ошибкой"](../Images/HowToWorkWithLocalizedLM5.png)  

### 2.1 Добавление ошибки в шаг  

- Нажать кнопку “+”  
![Кнопка "+"](../Images/HowToWorkWithLocalizedLM6.png)  
- Из выпадающего списка необходимо выбрать имя ивента, который считается ошибкой, настроенный в ассете LessonManagerErrors  
![Выбор целевого ивента](../Images/HowToWorkWithLocalizedLM7.png)  
- Из выпадающего списка необходимо выбрать имя описания ошибки, настроенного в ассете LessonManagerErrors  
![Выбор описания ошибки](../Images/HowToWorkWithLocalizedLM8.png)  

### 2.2 Удаление ошибки из шага  

- Нажать на кнопку “-” под именем ивента  
![Удаление ошибки](../Images/HowToWorkWithLocalizedLM9.png)  
  
Если текста ошибки нет ни в одном значении выпадающего списка, доступного из LM, то необходимо добавить его в ассет LessonManagerErrors ([См. Приложение 1](#приложение-1-работа-с-ассетом-lessonmanagererrors))  

</details>

## 3. Настройка аудиоподсказок в LM  

## Аудиоподсказки  

## Текстуры, материалы и что-то еще  

## Приложение 1 (Работа с ассетом LessonManagerErrors)  
<details>
<summary>Раскрыть</summary>

### П.1.1 Создание ассета  

- Создать ассет LessonManagerErrors (ПКМ->Create->LessonManagerErrors)  
![Создание ассета LessonManagerErrors](../Images/HowToWorkWithLocalizedLM10.png)  
- В инспекторе включить Debug-режим (троеточие в правом верхнем углу инспектора -> Debug)  
![Включение Debug-режима инспектора](../Images/HowToWorkWithLocalizedLM11.png)  
- В поле SceneName ввести название сцены тренажера для которого проводятся действия  
![Установка целевой сцены для ассета](../Images/HowToWorkWithLocalizedLM12.png)  
- В инспекторе включить нормальный режим (троеточие в правом верхнем углу инспектора -> Normal)  
![Включение нормального режима инспектора](../Images/HowToWorkWithLocalizedLM13.png)  

### П.1.2 Добавление отслеживаемого ивента  

- Нажать кнопку "Add error"  
![Кнопка "Add error"](../Images/HowToWorkWithLocalizedLM14.png)  
- Раскрыть созданное поле  
![Созданный элемент ассета](../Images/HowToWorkWithLocalizedLM15.png)  
- Ввести в поле ErrorKey имя ключа для этого ивента  
![Поле "ErrorKey"](../Images/HowToWorkWithLocalizedLM16.png)  
- Из выпадающего списка EventName выбрать ивент, который считается ошибкой  
![Ивенты тренажера](../Images/HowToWorkWithLocalizedLM17.png)  

### П.1.3 Добавление описания ошибки  

- Нажать кнопку "Add description for \[EventKey\]"  
![Кнопка "Add description for \[EventKey\]"](../Images/HowToWorkWithLocalizedLM18.png)  
- Раскрыть созданное поле  
![Добавленный ключ описания](../Images/HowToWorkWithLocalizedLM19.png)  
- В поле DescriptionKey ввести имя описания  
![Ключ описания](../Images/HowToWorkWithLocalizedLM20.png)  
- Из выпадающего списка TableCollection выбрать коллекцию таблиц, откуда брать локализацию  
![Коллекция таблиц](../Images/HowToWorkWithLocalizedLM21.png)  
- Из выпадающего списка LocalizationKeys выбрать ключ локализации  
![Ключ локализации](../Images/HowToWorkWithLocalizedLM22.png)  
- Нажать кнопку Save  
![Кнопка "Save"](../Images/HowToWorkWithLocalizedLM23.png)  

### П.1.4 Удаление ошибки  

- Если удаляемое описание единственное для ивента, то достаточно нажать на кнопку Delete event \[EventKey\] from asset  
![Кнопка "Delete event \[EventKey\] from asset"](../Images/HowToWorkWithLocalizedLM24.png)  
- Если у ивента, с которым связано описание оно не одно, то необходимо нажать кнопку Delete description \[DescriptionKey\]  
![Кнопка "Delete description \[DescriptionKey\]"](../Images/HowToWorkWithLocalizedLM25.png)  

В случае, если описание ошибки не присутствует ни в каком ключе локализации его необходимо добавить в таблицу локализации ([См. Приложение 2](#приложение-2-работа-с-таблицей-локализации-текстов))  

</details>

## Приложение 2 (Работа с таблицей локализации текстов)  
<details>
<summary>Раскрыть</summary>

### П.2.1 Создание теблицы локализации  

- Создать папку по пути Assets/Localization использовав в качестве названия название тренажера (Если папка существует, данный пункт пропустить)  
- Открыть окно редактирования таблиц локализации (Window->AssetManagment->LocalizationTables)  
![Как открыть окно редактирования таблиц локализации"](../Images/HowToWorkWithLocalizedLM26.png)  
- В открывшемся окне выбрать вкладку NewTableCollection  
![Вкладка NewTableCollection](../Images/HowToWorkWithLocalizedLM27.png)  
- В поле Type выбрать из выпадающего списка тип StringTableCollection  
![Поле Type](../Images/HowToWorkWithLocalizedLM28.png)  
- В поле Name ввести название таблицы (\[Имя тренажера\]Texts)  
![Поле Name](../Images/HowToWorkWithLocalizedLM29.png)  
- Нажать кнопку "Create"  
![Кнопка "Create"](../Images/HowToWorkWithLocalizedLM30.png)  
- В диалоговом окне указать путь к созданной ранее папке  

### П.2.2 Добавление значения в таблицу локализации  

- Из выпадающего списка выбрать редактируемую таблицу локализации  
![Выбор редактируемой таблицы локализации](../Images/HowToWorkWithLocalizedLM31.png)  
- Нажать кнопку "AddNewEntry"  
![Кнопка "AddNewEntry"](../Images/HowToWorkWithLocalizedLM32.png)  
- В ячейку на пересечении столбца "Key" и созданной строки ввести имя ключа добавляемого в таблицу  
![Ячейка для имени ключа](../Images/HowToWorkWithLocalizedLM33.png)  
- В ячейку на пересечении столбца "\[Имя языка на английском языке\]" и созданной строки ввести текстовое значение на данном языке  
![Ячейка для локализовнного текста](../Images/HowToWorkWithLocalizedLM34.png)  
### П.2.3 Удаление значения из таблицы локализации  

- Нажать кнопку "-" справа от имени ключа  
![Кнопка "-"](../Images/HowToWorkWithLocalizedLM35.png)  

### П.2.3 Синхронизация таблицы локализации текста с гугл таблицами  
<details>
<summary>Раскрыть</summary>

#### П.2.3.1 Создание и настройка подключения к гугл таблицам  

- Создать ассет GoogleSheetsProvider (ПКМ->Create->Localization->GooogleSheetProvider)  
![Создание ассета GoogleSheetsProvider](../Images/HowToWorkWithLocalizedLM36.png)  
- в поле ApplicationName вписать имя приложения в гугл-сурвисах (vr-trainers-localization)  
![Поле "ApplicationName"](../Images/HowToWorkWithLocalizedLM37.png)  
- Из выпадающего списка выбрать тип аутентификации OAuth  
![Выбор типа аутентификации](../Images/HowToWorkWithLocalizedLM38.png)  
- в поле ClientID вписать ID, выданный ответственным за приложение для синхронизации с гугл таблицами  
![Поле "ClientID"](../Images/HowToWorkWithLocalizedLM39.png)  
- В поле ClientSecret вписать пароль, выданный ответственным за приложение для синхронизации с гугл таблицами  
![Поле "ClientSecret"](../Images/HowToWorkWithLocalizedLM40.png)  
- Нажать кнопку Authorize  
![Кнопка "Authorize"](../Images/HowToWorkWithLocalizedLM41.png)  
- В открывшемся окне браузера выбрать гугл аккаунт, который будет использоваться для работы с гугл таблицами  
- Резальтатом таких действий должно стать сообщение в консоли "Authorized \[Дата\] \[Время\]"  
![Результат авторизации](../Images/HowToWorkWithLocalizedLM42.png)  

#### П.2.3.2 Настройка таблицы для последующей синхронизации с гугл таблицами  

- Выбрать ассет коллекции таблиц (Пример иконки ниже)  
![Пример иконки ассет коллекции таблиц](../Images/HowToWorkWithLocalizedLM43.png)  
- В блоке Extenshions нажать кнопку "+"  
![Кнопка "+"](../Images/HowToWorkWithLocalizedLM44.png)  
- Выбрать GoogleSheetExtenshions  
![Выбор типа расширения](../Images/HowToWorkWithLocalizedLM45.png)  
- В поле SheetsServiceProvider выбрать ассет провайдера гугл таблиц  
![Линковка GoogleSheetsProvider](../Images/HowToWorkWithLocalizedLM46.png)  
- В поле SpreadSheetID ввести ID гугл таблицы  
![Поле "SpreadSheetID"](../Images/HowToWorkWithLocalizedLM47.png)  
- Под полем SheetID ввести имя таблицы  
![Поле ввода имени нового листа](../Images/HowToWorkWithLocalizedLM48.png)  
- Нажать кнопку AddSheet  
![Кнопка "AddSheet"](../Images/HowToWorkWithLocalizedLM49.png)  
- Из выпадающего списка выбрать созданный лист  
![Выбор созданного листа](../Images/HowToWorkWithLocalizedLM50.png)  
- В блоке MapppedColumns нажать кнопку "+"  
![Кнопка "+"](../Images/HowToWorkWithLocalizedLM51.png)  
- Из выпадающего списка выбрать KeyColumn  
![Выбор типа ячейки "Key"](../Images/HowToWorkWithLocalizedLM52.png)  
- В блоке MapppedColumns нажать кнопку "+"  
![Кнопка "+"](../Images/HowToWorkWithLocalizedLM51.png)  
- Из выпадающего списка выбрать LocaleColumn  
![Выбор типа ячейки "Locale"](../Images/HowToWorkWithLocalizedLM53.png)  
- В поле LocaleIdentifier выбрать английскую локаль  
![Выбор английской локали](../Images/HowToWorkWithLocalizedLM54.png)  
- В блоке MapppedColumns нажать кнопку "+"  
![Выбор типа ячейки "Locale"](../Images/HowToWorkWithLocalizedLM51.png)  
- Из выпадающего списка выбрать LocaleColumn  
![Выбор типа ячейки](../Images/HowToWorkWithLocalizedLM53.png)  
- В поле LocaleIdentifier выбрать русскую локаль  
![Выбор русской локали](../Images/HowToWorkWithLocalizedLM55.png)  

#### П.2.3.3 Синхронизация серверной таблицы с таблицей в проекте  

- Выбрать ассет коллекции таблиц (Пример иконки ниже)  
![Пример иконки ассет коллекции таблиц](../Images/HowToWorkWithLocalizedLM43.png)  
- Нажать кнопку Push  
![Пример иконки ассет коллекции таблиц](../Images/HowToWorkWithLocalizedLM56.png)  

#### П.2.3.4 Синхронизация таблицы в проекте с серверной таблицей  

- Выбрать ассет коллекции таблиц (Пример иконки ниже)  
![Пример иконки ассет коллекции таблиц](../Images/HowToWorkWithLocalizedLM43.png)  
- Нажать кнопку Pull  
![Пример иконки ассет коллекции таблиц](../Images/HowToWorkWithLocalizedLM57.png)  

</details>

</details>

## Приложение 3 (Работа с ассетом AudioAdviceSO)  

## Приложение 4 (Работа с таблицей локализации ассетов)  
