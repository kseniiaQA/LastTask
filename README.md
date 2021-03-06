# План тестирования формы заявки для записи на курс "Тестирование ПО" 
В связи с тем, что необходимо протестировать отдельную часть функционала сайта Нетология необходимо использовать модульное тестирование. А именно, автоматизировать возможность записи на курс Тестировщик ПО. Это будет проверка функциональная проверка пользовательского интерфейса.
Автоматизированные сценарии включают в себя открытие страницы профессии "Тестировщик ПО". Добраться до странички профессии возможно несколькими способами:
1 нажав на картинку НЕО для начинающих и выбором профессии Тестировщик ПО
2 через выпадающие меню Каталог курсов - Программирование - Тестировщик ПО
3 через выпадающие меню Каталог курсов - Полный каталог
На самой страничке профессии есть несколько способов записи на курс. Функциональные тесты будут включать в себя как позитивные так и негативные кейсы. 
В позитивных тестах будет проверено, что при заполнение реальных имен, телефонов в формате +7 (999) 999 99 99 и почт в формате xxx@domen.ru, запись будет осуществлена.
Например, 
* Ксения
* +7 916 945 67 65
* kseniia@yandex.ru
* Ожидаемый результат: Заявка на запись курса создана, о чем сообщает всплывающее окно.

Негативные кейсы - проверка полей ввода на наличие валидации.
Отправка пустой формы. 
Ожидаемый результат: Надпись Обязательное поле под каждым полем ввода.

1. Слишком короткое имя.
* a
* +7 916 945 67 65
* kseniia@yandex.ru
* Ожидаемый результат: Слишком короткое Имя.
2. Цифры в имени.
* 678
*  +7 916 945 67 65
* kseniia@yandex.ru
* Ожидаемый результат: Имя должно состоять из букв.
3. Неверный формат номера.
* Ксения
* 7 916 945 67 6
* kseniia@yandex.ru
* Ожидаемый результат: Номер в формате +7 (999) 999-99-99.
4. Короткий номер.
* Ксения
* 8 917
* kseniia@yandex.ru
* Ожидаемый результат: Слишком короткий номер.
5. Отсутствие @ в почте.
* Дмитрий
*  +7 916 945 67 65
* kseniiayandex.ru
* Ожидаемый результат: Неверный формат почты.
6. Отсутствует домен в почте.
* Ксения
*  +7 916 945 67 65
* kseniia@yandexru
* Ожидаемый результат: Неверный формат почты.

## Сценарии для нахождения формы записи 

## Запись через каталог курсов и нажатием кнопки "записаться" 
1. Нажать на кнопку "Каталог курсов"
2. Выбрать вкладку "Программирование"
3. Пролистать и выбрать "Тестировщик ПО"
4. Нажать на кнопку "Записаться"

## Запись через вкладку "Нео для начинающих" и нажатием кнопки "записаться" 

1. Нажать на кнопку "Нео для начинающих"
2. Во вкладке справа выбрать "Программирование"
3. Пролистать и выбрать "Тестировщик ПО"
4. Нажать на кнопку "Записаться"

## Запись через вкладку "Нео для начинающих" и пролистыванием вниз

1.Нажать на кнопку "Нео для начинающих"
2. Во вкладке справа выбрать "Программирование"
3. Пролистать и выбрать "Тестировщик ПО"
4. Пролистать всю страницу вниз чтобы найти форму для записи

## Запись через каталог курсов и пролистыванием вниз 
 1. Нажать на кнопку "Каталог курсов"
 2. Выбрать вкладку "Программирование"
 3. Пролистать и выбрать "Тестировщик ПО"
 4. Пролистать всю страницу вниз чтобы найти форму для записи

# Сценарий для заполнения формы 
 1. Вписать имя в поле для имени 
 2. Вписать номер телефона в форму для телефона
 3. Нажать на кнопку "Записаться"


# Перечень используемых инструментов с обоснованием выбора

### Язык программирования
  Java 
  
### Система сборки проектов 
Gradle 

### Intellij Idea 

В IDEA можно подключить множество зависимостей и плагинов, которые понадобятся нам для тестирования данного функционала. Сам инструмент удобен, интерфейс интуитивно понятен. Также IDEA является бесплатной, что не менее важно.

## Lombok
Используется для дополнительной функциональности в Java c помощью изменения исходного кода перед Java компиляцией.

### Selenide
Удобный и бесплатный фреймворк, который очень удобен для тестирования веб-интерфейсов. Так же прост в конфигурации.

### Junit Jupiter 
Предоставляет новые возможности для написания тестов и создания собственных расширений. В проекте реализован специальный TestEngine для запуска тестов на ранее описанной платформе.

### Headless Selenide 
Режим ,который позволяет прогонять тесты быстрее и с меньшими затратами ресурсов. 

### Браузер Google Chrome версией не ниже 92.
Браузер Google Chrome является наиболее популярным и стабильным браузером.

### Allure Report 
Данный инструмент будет необходим для предоставления отчетности по тестированию 

### Appveyor
Распределённый веб-сервис непрерывной интеграции, предназначенный для сборки и тестирования программного обеспечения расположенного на GitHub и других сервисах хранения исходного кода 


## Перечень необходимых разрешений/данных/доступов
* Данные для логина 
* Разрешение на выполнение автоматизированного тестирования
* Доступ к базе данных и API сайта.


## Перечень и описание возможных рисков при автоматизации
* При использовании реальных данных для логина - опасность утечки данных
* Возможность падения тестов в связи с изменениями сайта.
* Сложности с поиском правильных локаторов на странице.
* Возможность уронить сайт в ходе тестирования.


# Перечень необходимых специалистов для автоматизации
Junior/Middle QA со знанием Java 

# Интервальная оценка с учётом рисков (в часах)
На тестирование данного функционала понадобится 5 рабочих дня, 40 часов + 15%-25% времени на наступление рисков, Итого - 60 часов. 
 
