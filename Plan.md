## План автоматизированного тестирования
### Перечень автоматизируемых сценариев

#### Предусловие для тестовых кейсов 1-14
1. Открыть веб-сервис: http://localhost:8080/
1. Нажать кнопку "Купить"

#### Тест-кейс №1. Купить картой approved с валидными данными пользователя
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Появится уведомление "Операция одобрена банком"
1. В базе данных статус платежа APPROVED

#### Тест-кейс №2. Купить картой declined с валидными данными пользователя
1. В поле "Номер карты" ввести "4444 4444 4444 4442"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Появится уведомление "Ошибка! Банк отказал в проведении операции."
1. В базе данных статус платежа DECLINED

#### Тест-кейс №3. Купить с пустым полем "Номер карты"
1. Оставить поле "Номер карты" пустым
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Номер карты" подчеркивается красным, под полем появляется надпись "Неверный формат"
1. В базу данных операция не попадает

#### Тест-кейс №4. Купить с неправильным значением в поле "Номер карты"
1. В поле "Номер карты" ввести "1111 1111 1111 1111"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Появится уведомление "Ошибка! Банк отказал в проведении операции."
1. В базу данных операция не попадает

#### Тест-кейс №5. Купить картой approved со значением "00" в поле "Месяц"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "00"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Месяц" подчеркивается красным, под полем появляется надпись "Неверный формат"
1. В базу данных операция не попадает

#### Тест-кейс №6. Купить картой approved со значением "13" в поле "Месяц"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "13"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Месяц" подчеркивается красным, под полем появляется надпись "Неверный формат"
1. В базу данных операция не попадает

#### Тест-кейс №7. Купить картой approved с пустым полем "Месяц"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. Поле "Месяц" оставить пустым
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Месяц" подчеркивается красным, под полем появляется надпись "Обязательное поле"
1. В базу данных операция не попадает

#### Тест-кейс №8. Купить картой approved са значением "00" в поле "Год"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "00"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Год" подчеркивается красным, под полем появляется надпись "Неверный формат"
1. В базу данных операция не попадает

#### Тест-кейс №9. Купить картой approved са значением "20" в поле "Год"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "20"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Год" подчеркивается красным, под полем появляется надпись "Истёк срок действия карты"
1. В базу данных операция не попадает

#### Тест-кейс №10. Купить картой approved са значением "27" в поле "Год"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "27"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Год" подчеркивается красным, под полем появляется надпись "Неверно указан срок действия карты"
1. В базу данных операция не попадает

#### Тест-кейс №11. Купить картой approved с пустым полем "Год"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. Поле "Год" оставить пустым
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Год" подчеркивается красным, под полем появляется надпись "Обязательное поле"
1. В базу данных операция не попадает

#### Тест-кейс №12. Купить картой approved с пустым полем "Владелец"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "22"
1. Поле "Владелец" оставить пустым
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Владелец" подчеркивается красным, под полем появляется надпись "Обязательное поле"
1. В базу данных операция не попадает

#### Тест-кейс №13. Купить картой approved со значением "!@!#SAD" в поле "Владелец"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "!@!#SAD"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Владелец" подчеркивается красным, под полем появляется надпись "Неверный формат"
1. В базу данных операция не попадает

#### Тест-кейс №14. Купить картой approved с пустым полем "CVC/CVV"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. Поле "CVC/CVV" оставить пустым
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "CVC/CVV" подчеркивается красным, под полем появляется надпись "Обязательное поле"
1. В базу данных операция не попадает

//TODO: написать тестовый кейсы для тестирования Credit Gate
### Предусловие для тестовых кейсов 15-28
1. Открыть веб-сервис: http://localhost:8080/
1. Нажать кнопку "Купить в кредит"

#### Тест-кейс №15. Оформить в кредит картой approved с валидными данными пользователя
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Появится уведомление "Операция одобрена банком"
1. В базе данных статус покупки APPROVED

#### Тест-кейс №16. Оформить в кредит картой declined с валидными данными пользователя
1. В поле "Номер карты" ввести "4444 4444 4444 4442"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Появится уведомление "Ошибка! Банк отказал в проведении операции."
1. В базе данных статус покупки DECLINED

#### Тест-кейс №17. Оформить в кредит с пустым полем "Номер карты"
1. Оставить поле "Номер карты" пустым
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Номер карты" подчеркивается красным, под полем появляется надпись "Неверный формат"
1. В базу данных операция не попадает

#### Тест-кейс №18. Оформить в кредит с неправильным значением в поле "Номер карты"
1. В поле "Номер карты" ввести "1111 1111 1111 1111"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Появится уведомление "Ошибка! Банк отказал в проведении операции."
1. В базу данных операция не попадает

#### Тест-кейс №19. Оформить в кредит картой approved со значением "00" в поле "Месяц"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "00"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Месяц" подчеркивается красным, под полем появляется надпись "Неверный формат"
1. В базу данных операция не попадает

#### Тест-кейс №20. Оформить в кредит картой approved со значением "13" в поле "Месяц"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "13"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Месяц" подчеркивается красным, под полем появляется надпись "Неверный формат"
1. В базу данных операция не попадает

#### Тест-кейс №21. Оформить в кредит картой approved с пустым полем "Месяц"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. Поле "Месяц" оставить пустым
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Месяц" подчеркивается красным, под полем появляется надпись "Обязательное поле"
1. В базу данных операция не попадает

#### Тест-кейс №22. Оформить в кредит картой approved са значением "00" в поле "Год"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "00"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Год" подчеркивается красным, под полем появляется надпись "Неверный формат"
1. В базу данных операция не попадает

#### Тест-кейс №23. Оформить в кредит картой approved са значением "20" в поле "Год"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "20"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Год" подчеркивается красным, под полем появляется надпись "Истёк срок действия карты"
1. В базу данных операция не попадает

#### Тест-кейс №24. Оформить в кредит картой approved са значением "27" в поле "Год"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "27"
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Год" подчеркивается красным, под полем появляется надпись "Неверно указан срок действия карты"
1. В базу данных операция не попадает

#### Тест-кейс №25. Оформить в кредит картой approved с пустым полем "Год"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. Поле "Год" оставить пустым
1. В поле "Владелец" ввести "Ира"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Год" подчеркивается красным, под полем появляется надпись "Обязательное поле"
1. В базу данных операция не попадает

#### Тест-кейс №26. Оформить в кредит картой approved с пустым полем "Владелец"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "22"
1. Поле "Владелец" оставить пустым
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Владелец" подчеркивается красным, под полем появляется надпись "Обязательное поле"
1. В базу данных операция не попадает

#### Тест-кейс №27. Оформить в кредит картой approved со значением "!@!#SAD" в поле "Владелец"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "!@!#SAD"
1. В поле "CVC/CVV" ввести "999"
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "Владелец" подчеркивается красным, под полем появляется надпись "Неверный формат"
1. В базу данных операция не попадает

#### Тест-кейс №28. Оформить в кредит картой approved с пустым полем "CVC/CVV"
1. В поле "Номер карты" ввести "4444 4444 4444 4441"
1. В поле "Месяц" ввести "08"
1. В поле "Год" ввести "22"
1. В поле "Владелец" ввести "Ира"
1. Поле "CVC/CVV" оставить пустым
1. Нажать кнопку "Продолжить"
#### Ожидаемый результат:
1. Поле "CVC/CVV" подчеркивается красным, под полем появляется надпись "Обязательное поле"
1. В базу данных операция не попадает


### Перечень используемых инструментов с обоснованием выбора
* Intellij IDEA Ultimate - расширенная версия IDEA Community, содержит инструменты для работы с базами данных и SQL
* Java 11 - язык написания авто-тестов
* Lombok - библиотека для оптимизации кода в авто-тестах
* JUnit5 - платформа для написания авто-тестов и их запуска
* Gradle - система управления проектами
* Allure - фреймворк для создания наглядной картины выполнения тестирования, сохранении отчетности и хронологии тестирования.
* Git и GitHub - хранение кода и авто-тестов
* Docker - инструмент для запуска СУБД MySQL и PostgreSQL, а также образа Node.js
* Docker Compose - инструмент для запуска много-контейнерных приложений и удобного доступа к конфигурации в файле формата yml

### Перечень и описание возможных рисков при автоматизации
* проблемы с запуском SUT
* проблемы с запуском СУБД и подключением к БД
* проблемы со сборкой образа Node.js
* трудности в написании авто-тестов

### Интервальная оценка с учётом рисков (в часах)
| Этап работы | Время (в часах) |
| ------ | ----------- |
| Создание проекта в IDEA на базе Gradle и подключение Lombok, JUnit5, Allure. Добавление приложения(aqa-shop.jar), application.properties, каталога gate-simulator, | 1 |
| Создание Git репозитория и подключение его к локальному проекту | 0.1 |
| Настройка и запуск образов MySQl, PostgreSQL, Node.js  | 4 |
| Написание авто-тестов | 16 |
| Запуск веб-сервиса, прогон авто-тестов   | 2 |
| Подготовка отчётных документов по итогам тестирования | 1 |
| Подготовка отчётных документов по итогам автоматизации | 2 |
| Итого | 26 |
| Наступление рисков | 5 |
| Итого с учетом рисков | 31 |

### План сдачи работ (когда будут авто-тесты, результаты их прогона и отчёт по автоматизации)
| Работа для сдачи | Дата (в формате dd.mm) |
| ------ | ----------- |
| План автоматизации | 05.08 |
| Авто-тесты | 14.08 |
| Отчёт по автоматизации | 16.08 |