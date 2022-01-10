# Подсветка интерактивных объектов
Следуй за зелеными сферами и да вознагражден будешь! @Неизвестный тестер тренажеров


## Используемые цвета:

### Зеленый:

  Albedo color (RGBA): 0, 255. 2. 143

### Синий:

  Albedo color (RGBA): any, any, any, 0

  Emission color (HSV): 217.100.84 Intensity: 0

### Прозрачный:

  Albedo color (RGBA): 0, 0, 0, 0
  
  
## Используемые материалы:

### FullAlphaMaterial:

  Путь: Assets/VRCommonComponents/InternalAssets/Highlight/FullAlphaMaterial.mat

  Rendering Mode: Fade

  Цвет: Прозрачный

### HighlightTransparent:

  Путь: Assets/VRCommonComponents/InternalAssets/Highlight/HighlightTransparent.mat

  RenderingMode: Fade

  Цвет: Зеленый

### ShadowMaterial:

  Путь: Assets/VRCommonComponents/InternalAssets/Highlight/ShadowMaterial.mat
  
  RenderingMode: Transparent

  Цвет: Синий
  
  
## Используемые кастомные меши:

### Стрелка:

  Путь: Assets/VRCommonComponents/InternalAssets/Highlight/Models/TeleportMarker.fbx:move_location_icon
  
  
## Типы подсветки:
### Объекты, на которые надо кликнуть (ClickableObject):

  Меш: Стандартная сфера Unity

  Материал (Активный): HighlightTransparent

  Материал (Неактивный): FullAlphaMaterial

  Тип подсветки в LessonManager: ChangeMaterial

### Объекты которые надо взять (GrabbableObject):


  Меш: Стандартная сфера Unity

  Материал (Активный): HighlightTransparent

  Материал (Неактивный): FullAlphaMaterial

  Тип подсветки в LessonManager: ChangeMaterial


### Объекты на которые надо кликнуть рейкастом

  Меш: Стрелка

  Материал (Активный): HighlightTransparent

  Материал (Неактивный): FullAlphaMaterial

  Тип подсветки в LessonManager: ChangeMaterial


### Место, куда необходимо перенести объект:

  Меш: Объект, который необходимо перенести

  Материал: ShadowMaterial

  Тип подсветки в LessonManager: ActivateShadow
  
  
  

## Режимы тренажера
### Обучение:

  Вся подсветка активна

### Тренировка:

  Активна только подсветка места для переноса

### Экзамен

  Активна только подсветка места для переноса
