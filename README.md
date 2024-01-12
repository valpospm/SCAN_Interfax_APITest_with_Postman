# SCAN_Interfax_APITest_with_Postman
**Тестирование сервиса SCAN для АО "Интерфакс".**
Ссылка на Swagger UI: <a href="[https://t.me/CurrExchBot_bot](https://gateway.scan-interfax.ru/swagger/index.html#/)" target="_blank">https://gateway.scan-interfax.ru/swagger/index.html#/</a>
Алгоритм тестирования:
1. Создание переменных для логина и пароля: **_test_login_** и **_test_password_**. В эти переменные с помощью csv-файла передаются тестовые данные для логина и пароля. Тестирование логин и пароль с проведением 3-х позитивных и 5-и негативных тестов на статус-код 200.
2. Настройка авторизации для всех заголовков коллекции, динамически получая значение токена с помощью скрипта в запросе «Авторизация пользователя».
3. Получение текущего баланса пользователя. Запись текущего значения баланса в переменную коллекции **_current_balance_**.
4. Получение темы публикаций. Создание переменных коллекции **_subjects_name1_**, **_subjects_name2_**, **_subjects_name3_** и запись в них наименования тем первых трёх публикаций. Создание переменной коллекции **_subjects_total_** и запись в неё общего количества публикаций.
5. Получение документов в формате ScanDoc по идентификаторам одним запросом. Передача на сервер два идентификатора в виде переменных:

   
   а) _"1:0JPQqdGM0JNWCdCzf2Jt0LHQotGV0ZUh0ZbRlBXCt0Je0JHQruKAnDcUXkZQ0YvQscKnehLRnNC1KtGK0Ll9BWLigLo/HXXCrhw="_

   
   б) _"1:fmYoHEjQrRbQhz3RiUtm4oCh0JLRmtCLIyU10IzigqzRgGjQmCoR0JFg0YRhwrVzN9CxDUM50KcpdTbRiNCLwpjRkuKAphXRkVxh0JU50K5uWdC50L7RjX0C0KwQRsKp"_
   Получение из ответа наименования новостных агентств и их запись в переменные коллекции **_news_agent_1_** и **_news_agent_2_** в сопровождении запроса 
   тестом на статус-код 200.
