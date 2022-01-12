# Основы работы с DocFx (Создание пустого сайта болванки)

[Официальная инструкция по работе с DocFX](https://dotnet.github.io/docfx/)

Скачайте docfx с офф сайта см. выше и распакуйте (в примере C:\...SomeDir...\docfx)

Далее по тексту происходит работа в CMD:

set PATH=%PATH%;C:\...SomeDir...\docfx - Добавить в PATH (окружение)

Создаем директорию для проекта с документацией (в примере D:\docfx_walkthrough)

cd /d D:\docfx_walkthrough - в cmd переходим в эту директорию
    Примечание: Команда cd без параметра /d (d - это не название диска а команда) не меняет диск. Или до команды, или после выполните переход на диск.

D:\docfx_walkthrough>docfx init -q -инициализировать проект с документацией

D:\docfx_walkthrough>docfx docfx_project/docfx.json - создать сайт с документацией
    Примечание: После любых изменений вызываем эту команду что бы пересобрать сайт

D:\docfx_walkthrough>docfx serve docfx_project/_site - запустить сайт на локальном сервере (для проверки http://localhost:8080/)
    Примечание: Как перестанет быть нужным пишем команду stop


## Как наполнить пустой сайт болванку 

Далее нужно собрать метафайлы для наполнения API документации
Нам не подходит дефолтный вариант когда метафайлы собираются из решения Assembly-CSharp.csproj проекта т.к при исполнении команды падают Warnings
Warning:[ExtractMetadata](D:/Learning/KnowledgeIsPower/Assembly-CSharp.csproj)Workspace failed with: [Warning] Found project reference without a matching metadata reference: D:\Learning\KnowledgeIsPower\SimpleInput.Runtime.csproj

Они порождают следующие Warnings:
Warning:[ExtractMetadata]Workspace failed with: [Failure] Файл 'D:\Learning\KnowledgeIsPower\docfx_project\src\Assets\CodeBase\Infrastructure\AssetManagement\AssetProvider.cs' не найден.

По причине: 
Это когда в проекте есть ссылка на проект, которую нельзя сопоставить с выходным путем (кодом).
Это происходит с многоцелевыми проектами (проект на целен на Unity решение).

Но нам подходит вариант когда мы собираем мета данные прямо из файлов скриптов для того что бы мы ориентировались на скрипты 
а не на решения необходимо поменять строки в файле docfx.json 

Параметров: src, files Для примера использованна ссылка на проект который находился на том же диске где и проект с документацией "D:\Learning\KnowledgeIsPower"

```
"metadata": [
    {
     "src": [
       {
         "src": "../. ./",
         "files": [
           "Learning/KnowledgeIsPower/Assets/CodeBase/**.cs"
         ]
       }
     ],
     "dest": "api",
     "disableGitFeatures": false,
     "disableDefaultFilter": false
   }    
 ],

```

Так же в этом файле что бы появилась поисковая строка в правом верхнем углу на всех статьях
необходимо в этом же файле добавить строку

```
"postProcessors": [ "ExtractSearchIndex" ]

```

После редактирования этого файла нужно запустить создания мета данных

D:\docfx_walkthrough>cd D:\docfx_walkthrough\docfx_project - переходим в каталог docfx_project проекта документации

D:\docfx_walkthrough\docfx_project>docfx metadata - создаем мета данные из библиотеки классов

D:\docfx_walkthrough\docfx_project>cd D:\docfx_walkthrough - переходим обратно в корень проекта документации

D:\docfx_walkthrough>docfx docfx_project/docfx.json - пересобираем проект с документацией т.к. были изменения

D:\docfx_walkthrough>docfx serve docfx_project/_site - запустить сайт на локальном сервере (для проверки http://localhost:8080/)
    Примечание: Как перестанет быть нужным пишем команду stop

Что бы добавить новые разделы, после создании папки соответсвующего раздела и занесения его в toc.yml 
корня проекта необходимо занести этот каталог как параметр в файл docfx.json

Пример:

```
"build": {
   "content": [
     {
       "files": [
         "api/**.yml",
         "api/index.md"
       ]
     },
     {
       "files": [
         "articles/**.md",
         "articles/**/toc.yml",
         "toc.yml",
         "*.md"
       ]
     },
     {
       "files": [
         "developmentPipline/**"
       ]
     },
     {
       "files": [
         "simulatorDevelopmentGuide/**"
       ]
     }
   ],
```