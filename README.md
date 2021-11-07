# gosuslugi-qr-code

HTML страничка с логикой распознания QR кода от ГосУслуг.


## Требования

Мне нужен файл написанный на html при запуске которого в браузере на любом компьютере он бы подключался к установленной 
WEB камере на этом компе и при поднесении QR кода о вакцинации, анализировал его и переходил на гос. услуги, так же как 
если делать все с мобильного телефона. 

При поднесении следующего QR кода к камере должен происходить снова анализ QR кода и переход на сайт гос. услуг.

Если QR код вообще какой то левый, допустим от пачки с чипсами, то на экран должно выводится предупредительное сообщение

Для анализа QR кода нужно использовать какую-то открытую библиотеку

Вот что то нашел на просторах интернета:
* https://github.com/cozmo/jsQR/tree/master/docs
* https://github.com/zxing-js/library
* https://zxing-js.github.io/library/
* https://webqr.com/contact.html


## Детали реализации

Библиотеки выкачиваются из публично доступного хранилища библиотек - https://unpkg.com:
* библиотека расшифровки QR-кодов https://www.npmjs.com/package/html5-qrcode
* библиотека отображения сообщений пользователю https://www.npmjs.com/package/sweetalert2
* библиотека верстки https://getbootstrap.com/docs/4.6/


## Запуск

Т.к. библиотеки выкыачиваются извне, то достаточно просто открыть страницу в браузере, или настроить любой web-сервер
для отдачи ее, как статичного содержимого.

Для удобства можно пользоваться `docker-compose.yaml` файлом:
* установить docker. https://www.docker.com
* установить docker-compose. https://docs.docker.com/compose/
* выполнить `docker-compose up` в корневой папке проекта

Приложение будет развернуто на порту 8000, он указан в `docker-compose.yaml` файле. Будет слушать интерфейс 0.0.0.0.
 

# Заметки

## Ссылки на рассмотренные библиотеки/инструменты для распознания QA кодов

* https://www.npmjs.com/package/html5-qrcode
    * https://github.com/mebjas/html5-qrcode
    * https://blog.minhazav.dev/research/html5-qrcode#scan-using-file
    * https://minhazav.medium.com/qr-code-scanner-using-html-and-javascript-3895a0c110cd
    * **РЕЗУЛЬТАТ** - chosen. Works out-of-the-box, API is clean and convenient

* https://www.npmjs.com/package/@zxing/library
    * https://github.com/zxing-js/library
    * **РЕЗУЛЬТАТ** - не рассматривали

* https://www.npmjs.com/package/jsqr
    * https://github.com/cozmo/jsQR
    * **РЕЗУЛЬТАТ** - не рассматривали

* https://www.npmjs.com/package/instascan
    * https://www.js-tutorials.com/javascript-tutorial/how-to-scan-qr-reader-using-javascript-and-html5/
    * https://www.youtube.com/watch?v=hJAY4JUPxus
    * https://pretagteam.com/question/read-qrcode-from-a-web-page-with-camera
    * **РЕЗУЛЬТАТ** - не рассматривали

* https://www.npmjs.com/package/qr-scanner
    * https://github.com/nimiq/qr-scanner
    * (based on cozmo/jsQR and ZXing)
    * **РЕЗУЛЬТАТ** - не рассматривали

* https://github.com/LazarSoft/jsqrcode
    * (This is a port of ZXing qrcode scanner)
    * https://webqr.com/index.html
    * https://gist.github.com/bobvanderlinden/a58f39e44dba53e17cd2e2ec4774af08
    * https://searchcode.com/codesearch/view/66607988/
    * **РЕЗУЛЬТАТ** - не стали использовать. это библиотека для серверных приложений

* https://www.npmjs.com/package/qrcode
    * **РЕЗУЛЬТАТ** - не стали использовать. это библиотека для серверных приложений

* https://www.npmjs.com/package/web-qr
    * **РЕЗУЛЬТАТ** -  не стали использовать, т.к. не поддерживается ее разработчиком

* https://www.npmjs.com/package/jsqrcode
    * **РЕЗУЛЬТАТ** -  не стали использовать, т.к. не поддерживается ее разработчиком

* https://www.npmjs.com/package/@lostinbrittany/jsqrcode
    * **РЕЗУЛЬТАТ** -  не стали использовать, основана на "LazarSoft/jsqrcode". не поддерживается ее разработчиком


## Папка "examples"

Содержит пример QR кодов, сгенерировано с помощью https://goqr.me
* HELLO_WORLD.png  -  внутри текст `"HELLO_WORLD"`


## Примеры подключение библиотек

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<script src="https://rawgit.com/schmich/instascan-builds/master/instascan.min.js"></script>
<script src="https://unpkg.com/html5-qrcode@2.1.2/html5-qrcode.min.js"></script>
```
