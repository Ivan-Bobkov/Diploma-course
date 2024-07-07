Тестирование страницы https://b2c.passport.rt.ru сайта "Ростелеком"

При тестировании сайта были написаны: ручные чек-лист, тест-кейсы и баг- репорты: автоматизированные тесты. 

При тестировании сайта были применены следующие техники тест-дизайна:
анализ граничных значений; 
разбиение на классы эквивалентности; 
тестирование состояний и переходов. 

Используемые при тестировании библиотеки PyCharm:
requests python-dotenv pytest selenium faker Автотесты настроены на запуск через Run.

Для страниц восстановления пароля в позитивных и негативных тестах необходимо ВРУЧНУЮ вводить символы с картинки “капчи” в поле для ввода “капча”, задержка по времени для ввода настроена автоматически. Для проверки авторизации по почте и паролю, так же потребуется ввод капчи вручную!!!

Для генерации временного адреса электронной почты использовался сайт: https://www.1secmail.com/

Проект содержит две папки: pages и tests, а так же файл: conftest.py
conftest.py - фикстура для работы с браузером.

Папка pages содержит следующие файлы:
registration_email.py - GET-запросы к виртуальному почтовому ящику для получения валидного email и кода для регистрации на сайте и восстановления пароля;
config.py - основной URL тестируемого сайта;
auth.py - функции-обертки для локаторов, распределенные по классам в зависимости от тематики тестов;
base.py - функции для применения к локаторам явных ожиданий, получения главной страницы сайта и пути текущей страницы;
locators.py - XPath- и CSS-локаторы web-элементов сайта;
settings.py - данные, используемые в процессе теста.

Папка tests содержит следующие файлы:
test_registr_positive - позитивные тесты страницы регистрации;
test_auth_page_positive - позитивные тесты страницы авторизации;
test_new_password_positive - позитивные тесты страницы восстановления пароля;
test_registr_positive - позитивные тесты страницы регистрации;
test_auth_page_negative - негативные тесты страницы авторизации;
test_new_password_negative - негативные тесты страницы восстановления пароля.
