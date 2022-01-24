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

## 3. Настройка аудиоподсказок в LM  

## Аудиоподсказки  

## Текстуры, материалы и что-то еще  

## Приложение 1 (Работа с ассетом LessonManagerErrors)

### Создание ассета

- Создать ассет LessonManagerErrors (ПКМ->Create->LessonManagerErrors)  
![Создание ассета LessonManagerErrors](../Images/HowToWorkWithLocalizedLM10.png)  
- В инспекторе включить Debug-режим (троеточие в правом верхнем углу инспектора -> Debug)  
![Включение Debug-режима инспектора](../Images/HowToWorkWithLocalizedLM11.png)  
- В поле SceneName ввести название сцены тренажера для которого проводятся действия  
![Установка целевой сцены для ассета](../Images/HowToWorkWithLocalizedLM12.png)  
- В инспекторе включить нормальный режим (троеточие в правом верхнем углу инспектора -> Normal)  
![Включение нормального режима инспектора](../Images/HowToWorkWithLocalizedLM13.png)  

### Добавление отслеживаемого ивента

- Нажать кнопку "Add error"  
![Кнопка "Add error"](../Images/HowToWorkWithLocalizedLM14.png)  
- Раскрыть созданное поле  
![Созданный элемент ассета](../Images/HowToWorkWithLocalizedLM15.png)  
- Ввести в поле ErrorKey имя ключа для этого ивента  
![Поле "ErrorKey"](../Images/HowToWorkWithLocalizedLM16.png)  
- Из выпадающего списка EventName выбрать ивент, который считается ошибкой  
![Ивенты тренажера](../Images/HowToWorkWithLocalizedLM17.png)  

### Добавление описания ошибки

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

### Удаление ошибки

- Если удаляемое описание единственное для ивента, то достаточно нажать на кнопку Delete event \[EventKey\] from asset  
![Кнопка "Delete event \[EventKey\] from asset"](../Images/HowToWorkWithLocalizedLM24.png)  
- Если у ивента, с которым связано описание оно не одно, то необходимо нажать кнопку Delete description \[DescriptionKey\]  
![Кнопка "Delete description \[DescriptionKey\]"](../Images/HowToWorkWithLocalizedLM25.png)  

## Приложение 2 (Работа с таблицей локализации)

Cоздать коллекцию таблиц локализации
Создать папку по пути Assets/Localization использовав в качестве названия название тренажера
Открыть окно редактирования таблиц локализации (Window->AssetManagment->LocalizationTables)
В открывшемся окне выбрать вкладку NewTableCollection
В поле Type выбрать из выпадающего списка тип StringTableCollection
В поле Name ввести название таблицы (\[Имя тренажера\]Texts)
Нажать кнопку Create
В диалоговом окне указать путь к созданной папке в п. i
В инспекторе выбрать файл сохранения ошибок тренажера
Выбрать локаль из выпадающего списка для заполнения (скорее всего нужно будет выбрать “RU”)
Перетащить созданную в п.а коллекцию таблиц локализации в поле TableCollection
Нажать кнопку FillTable
(Опционально) Залить таблицу в облако
Выбрать ассет коллекции таблиц, созданный в п.а. (Пример иконки ниже)
Под полем SheetID ввести имя таблицы
Нажать кнопку AddSheet
Из выпадающего списка выбрать созданную таблицу
Нажать кнопку Push

## Приложение 3 (Работа с ассетом AudioAdviceSO)
