Версия: 1.9

Дата публикации: 05.05.2015

Что нового?
-----------

Orchard 1.9 включает исправление ошибок, а также новый фукнционал и доработки:

* Переход на Microsoft .NET 4.5.1
* Модуль Audit Trail
* Поддержка черновиков в виджетах
* Индексирование черновиков
* Локализация дат и улучение работы календаря
* Модуль Dynamic Layout
* Модуль Dynamic Forms
* Улучшения механизма кеширования
* Поддержка OWIN middlewares
* Обновление ASP.NET MVC до версии 5.2
* Обновление .NET Framework до версии 4.5.1
* Обновление Microsoft Azure SDK до версии 2.5
* Добавлена поддержка Azure Redis Cache
* Обновление TinyMCe до версии 4
* Улучшение работы мезанизма локализации
  * Поддержка RTL
  * Возможность выбор культуры (в панели администрирования и для пользователей)
* Message Bus
* Виджеты поиска
* Алгорит хеширования паролей изменен на PBKDF2

Полный список исправленых ошибок можно посмотреть [здесь](https://github.com/OrchardCMS/Orchard/issues?q=is%3Aissue+milestone%3A%22Orchard+1.9%22+is%3Aclosed).

Обновление с предыдущей версии
--------------------------------------

Руководство по обновлению находится здесь: <http://docs.orchardproject.net/Documentation/Upgrading-a-site-to-a-new-version-of-Orchard>.

Вне зависимости от выбранного способа обновления, мы рекомендуем предварительно сделать резервную копию вашего сайта и базы данных.

### Обновление с версии 1.8.2 и ниже

Для обновления следуйте инструкциям по ссылке: <http://docs.orchardproject.net/Documentation/orchard-1-8-2.release-Notes>

#### Обновление модулей

В Orchard версии 1.9 был осуществлен переход с .NET Framework версии 4.5 на версию 4.5.1. Для корректной компиляции вам потребуется выставить такую же версию в настройках ваших модулей.

В связи с обновлением Azure SDK до версии 2.5 большинство библиотек, связанных с работой Azure, были обновлены. Некоторые изменения могут привести к некорректной работе ваших библиотек, поэтому, если вы используете данный механизм, мы рекомендуем предварительно проверить ваши сайты и модули на совместимость с данной версией.

#### Примечание о смене алгоритма хэширования паролей по умолчанию

Алгоритм хэширования, используемый по умолчанию для хранения паролей пользователей был изменен с SHA1 на  PBKDF2 (если быть точнее, то на его реализацию `System.Web.Helpers.Crypto.HashPassword()`).

По умолчанию все пароли будут мигрированы на новый алгоритм в момент первого входа пользователей в систему. Если вы хотите продолжить использовать прежний алгоритм SHA1, добавле параметр `"Orchard.Users.KeepOldPasswordHash"` и значение `"true"` в конфигурацию appSettings или connectionString в вашем файле Web.config (или аналоге).

#### Примечание об улучшении работы рецептов при установке

Теперь при установке система сама определяет наличие рецептов в Ваших модулях и выводит их на странице установки. Это означает, что больше нет необходимости добавлять ваши рецепты в модуль Orchard.Setup, теперь их можно хранить в ваших модулях.

Нужно иметь ввиду, что для появления на странице установки в метаданных рецепта должен быть указан параметр IsSetupRecipe (см. рецепты в Orchard.Setup).

Авторы
------------

Orchard CMS существует благодаря сообществу. Мы хотели бы поблагодарить разработчиков, участвовавших в данном выпуске системы:

- Abhishek Luv	([abhishekluv](http://www.codeplex.com/site/users/view/abhishekluv))
- Arjan Noordende	([anoordende](http://www.codeplex.com/site/users/view/anoordende))
- Antoine Griffard	([agriffard](http://www.codeplex.com/site/users/view/agriffard))
- Benedek Farkas	([nightwolf226](https://www.codeplex.com/site/users/view/nightwolf226))
- Benjamin Grabkowitz	([bgrabkowitz](https://www.codeplex.com/site/users/view/bgrabkowitz))
- Bertrand Le Roy	([bertrandleroy](http://www.codeplex.com/site/users/view/bertrandleroy))
- Bill Cooper	([bill_cooper](http://www.codeplex.com/site/users/view/bill_cooper))
- Brett Morrison	([morrisonbrett](https://www.codeplex.com/site/users/view/morrisonbrett))
- Bryan Porter	([brporter](https://www.codeplex.com/site/users/view/brporter))
- Christian Surieux	([csadnt](http://www.codeplex.com/site/users/view/csadnt))
- Claire Botman	([planetClaire](https://www.codeplex.com/site/users/view/planetClaire))
- Dain Kaplan	
- Daniel Dabrowski	([rodpl](https://www.codeplex.com/site/users/view/rodpl))
- Daniel Stolt	([Decorum](https://www.codeplex.com/site/users/view/Decorum))
- Denis Besic	([besicdenis](https://www.codeplex.com/site/users/view/besicdenis))
- Eric Perez	([codereached](https://www.codeplex.com/site/users/view/codereached))
- Gilian Keulens	([Walance](http://www.codeplex.com/site/users/view/Walance))
- Jack Cheng	([jchenga](https://www.codeplex.com/site/users/view/jchenga))
- Jay Harris	([jayharris](https://www.codeplex.com/site/users/view/jayharris))
- Jason Burgard	([jburgard](https://www.codeplex.com/site/users/view/jburgard))
- Jasper Dunker	([jasperd](http://www.codeplex.com/site/users/view/jasperd))
- Jorge Castillo Pino ([jcastillopino](http://www.codeplex.com/site/users/view/jcastillopino))
- Jean-Thierry Kéchichian	([jtkech](https://www.codeplex.com/site/users/view/jtkech))
- Jeff Bullock	([j3ffb](https://www.codeplex.com/site/users/view/j3ffb))
- Josh Berry	([joshby](https://www.codeplex.com/site/users/view/joshby))
- Katsuyuki Ohmuro	([kohmuro](https://www.codeplex.com/site/users/view/kohmuro))
- Kegan Maher	([thekaveman](https://www.codeplex.com/site/users/view/thekaveman))
- Mark Loveland-Armour	([forsvarir](https://www.codeplex.com/site/users/view/forsvarir))
- Matt Varblow	([mvarblow](https://www.codeplex.com/site/users/view/mvarblow))
- Michael Yates	([mjy78](http://www.codeplex.com/site/users/view/mjy78))
- Nicholas Mayne	([Jetski5822](http://www.codeplex.com/site/users/view/Jetski5822))
- Paul Devenney	
- Piotr Szmyd	([pszmyd](https://www.codeplex.com/site/users/view/pszmyd))
- Sebastien Ros	([sebastienros](http://www.codeplex.com/site/users/view/sebastienros))
- Sotirios Roussos	([urbanit](http://www.codeplex.com/site/users/view/urbanit)
- Sipke Schoorstra	([sfmskywalker](http://www.codeplex.com/site/users/view/sfmskywalker))
- Stanley Goldman	([StanleyGoldman](http://www.codeplex.com/site/users/view/StanleyGoldman))
- Thierry Fleury	([Codinlab](https://www.codeplex.com/site/users/view/Codinlab))
- Wojciech Gadzinski	([Ermesx](https://www.codeplex.com/site/users/view/Ermesx))
- 	([Xeevis](https://www.codeplex.com/site/users/view/Xeevis))
- Zoltán Lehóczky	([Piedone](http://www.codeplex.com/site/users/view/Piedone))
- Baruch Nissenbaum	([qt1](http://www.codeplex.com/site/users/view/qt1))