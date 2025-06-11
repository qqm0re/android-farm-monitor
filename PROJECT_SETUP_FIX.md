# Инструкция по исправлению ошибки с пакетом в Android проекте

## Проблема
Ошибка: "The declared package ... does not match the expected package ..." возникает из-за несоответствия настроек IDE и структуры проекта.

## Возможные причины
- Неправильно настроена корневая папка исходников (source root)
- Неправильная структура папок относительно пакета
- Кэш или настройки Gradle/IDE устарели

## Шаги для исправления

1. Откройте проект в Android Studio или VSCode с Android плагинами.

2. Проверьте структуру папок:
   - Исходники должны находиться в `app/src/main/java/com/example/androidfarmmonitor/`
   - Пакет в Java файлах должен быть `package com.example.androidfarmmonitor;`

3. Установите `java` папку как Source Root:
   - В Android Studio: Правый клик на папку `java` -> Mark Directory as -> Sources Root

4. Обновите проект Gradle:
   - В Android Studio: File -> Sync Project with Gradle Files

5. Очистите кэш IDE:
   - В Android Studio: File -> Invalidate Caches / Restart

6. Проверьте файл `build.gradle` (Module: app):
   - Убедитесь, что sourceSets настроены по умолчанию:
     ```
     android {
         ...
         sourceSets {
             main.java.srcDirs = ['src/main/java']
         }
     }
     ```

7. Перезапустите IDE и пересоберите проект.

## Дополнительно
Если используете VSCode, убедитесь, что расширения для Android и Java корректно настроены и проект открыт в корне AndroidFarmMonitor.

---

Если после выполнения этих шагов проблема сохраняется, пожалуйста, сообщите, я помогу с дальнейшей диагностикой.
