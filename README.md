PushBullet for MajorDoMo
========================
Доведенный мною до работоспособного состояния форк https://github.com/dimaw/PushBullet-for-MajorDoMo
Исправлены функции авторизации, получения списка устройств; добавлена функция рассылки на все устройства в базе.
Также добавлен файл с сертификатом для авторизации на сервисе (информация взята у ivkos).
ВНИМАНИЕ! Для работоспособности на windows нужно скачать curl с поддержкой ssl.

Тема на форуме http://majordomo.smartliving.ru/forum/viewtopic.php?f=7&t=1776
Для взаимодействия с сервисом PushBullet использована библиотека: https://github.com/ivkos/PushBullet-for-PHP

##Требования:
* PHP >= 5.2.0
* библиотека cURL для PHP
* PushBullet API key (доступен здесь: https://www.pushbullet.com/account)

После установки, в базе создается таблица app_pushbullet, где хранятся необходимые apykey и iden-ы устройств.
Каждому iden соответствует наименование устройста, по которому становится возможним к нему и обращаться.

##Пример использования:
```php
include_once(ROOT.'modules/app_pushbullet/app_pushbullet.class.php');

//простое сообщение
push_note('GT-I9100', 'Заголовок', 'Текст сообщения');

//сообщение в виде списка
push_list('GT-I9100', 'Купи в магазине:', array("Хлеб", "Колбаса"));

//адрес со ссылкой на картах google
push_address('GT-I9100', 'Заголовок', 'Москва, Шаболовка, 37');

//файл
push_file('GT-I9100', '/var/www/images/trees.jpg'); 

//ссылка
push_link('GT-I9100', 'MajorDoMo', 'http://smartliving.ru');
```
