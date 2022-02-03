# Ahegao API -> Kodik API -> video

* Базовая ссылка для этого класса методов: 

`API_URL = "api.ohegao.ovh/kodik/video.<PARAMS>"`

### **video**

* Обозначения: 

1. " <span style="color:#9700ff">☑</span> " - Параметр обязателен.
2. " <span style="color:#9700ff">☐</span> " - Параметр не обязателен.


#### **video.info**

**Этот метод достает инфу из API Кодика, Шики и Аниксарта**


* Обращение:
    * Протокол: <span style="color:#02e400">GET</span>
    * Необходимо:
        * Payload - Данные запроса:
            * <span style="color:#9700ff">☑</span> src: <span style="color:#f1c232">str</span>; Название или ссылка на то, что ищем.
            * <span style="color:#9700ff">☐</span> by: <span style="color:#f1c232">str</span>; (default) link  - через ссылку; name - по имени;
            * <span style="color:#9700ff">☑</span> token: <span style="color:#f1c232">str</span>; Ваш токен авторизации.
    * Пример: `GET kodik/video.info?src=<SRC_URL>&by=<LINK_OR_NAME>&token=<TOKEN>`
* Ответ:
    * Тип: json
    
```json title="Ответ сервера"
{
"code": 0,  // int
"object": {
  "title": "Хвост Феи", // Название на русском
  "title_en": "Fairy Tail", // Название на английском
  "title_orig": "Fairy Tail", // Оригинальное(на Японском или Китайском) название
  "pic": "https://moe.shikimori.one/system/animes/original/6702.jpg", // Картинка(не превью)
  "shiki": "https://shikimori.one/animes/6702-fairy-tail", // ссылка на шики
  "releaseyear": 2009, // Год релиза(тип int)
  "releasestatus": "released", // Статус выхода: ongoing - выходит сейчас; released - вышел; announce - анонс.
  "eps": 175, // Эпизодов(тип int)
  "score": 4.92, // Оценки, указываются до 5(тип float)
  "mangaauthor": "Hiro Mashima", // Автор манги(инфа с шики)
  "director":  "Shinji Ishihira", // Режиссер
  "tags": [ //
    "romantic": false, // boolean
    "comedy": true,  // boolean
    // ...
    ],
    "casts": [
      "anilibria": true, // boolean
      "anidub": false,  // boolean
    ]
  }
}
```


#### **video.link**

* Обращение:
    * Протокол: <span style="color:#02e400">GET</span>
    * Необходимо:
        * Payload - Данные запроса:
            * <span style="color:#9700ff">☑</span> src: <span style="color:#f1c232">str</span>; Cсылка на плеер.
            * <span style="color:#9700ff">☑</span> token: <span style="color:#f1c232">str</span>; Ваш токен авторизации.
    * Пример: `GET kodik/video.info?src=<SRC_URL>&token=<TOKEN>`
* Ответ:
    * Тип: json

```json title="Ответ сервера"
{
"code": 0,
"object": {
  "link": "blob:https://aniqit.com/..."
  }
}
```

???+ note "Обратите внимание!"
       К вашему вниманию: у нас нет возможности декодировать blob-ы, так как они довольно непросто устроены, если вы используете JS в своем проекте можете использовать [это](https://stackoverflow.com/questions/14952052/convert-blob-url-to-normal-url)