/manga
=====

.. _/getInfo:

/getInfo
------------

Этот метод достает инфу из API Шики и парсит Readmanga:

.. code-block:: console

   /kodik/getInfo?src=  -  название или ссылка на то, что ищем *ОБЯЗАТЕЛЬНЫЙ
                  token=   -  токенский(не токийский!) *ОБЯЗАТЕЛЬНЫЙ
                  by=   -  как ищем(link - через ссылку; name - по имени) *ОБЯЗАТЕЛЬНЫЙ
Вывод:

.. code-block:: console

    {
    "code": 200 // int
    "object":
               {
               "title": "Милые деньки с мальчиком", // Название на русском
               "title_en": "Sweet Days With a Boy", // Название на английском
               "title_orig": "少年を飼う", // Оригинальное(на Японском или Китайском) название
               "pic": "https://staticrm.rmr.rocks/uploads/pics/01/76/626.jpg", // Картинка(не превью)
               "shiki": "https://shikimori.one/...", // ссылка на шики
               "releaseyear": 2017, // Год релиза(тип int)
               "releasestatus": "ongoing", // Статус выхода: ongoing - выходит сейчас; released - вышел; announce - анонс.
               "score": 4.12, // Оценки, указываются до 5(тип float)
               "author": "Dagiwara Daisuke", // Автор манги(инфа с шики)
               "tags": [ //
                  "romantic": true, // boolean
                  "comedy": true,  // boolean
                  // ...
               ],
               "translators": [
                  "Ксавиадиорб", // boolean
                  "boyчик 337",  // boolean
               ]
           }
    }
   

.. _/getChapter:

/getChapter
------------
Получает ссылки на картинки страниц определенной главы, определенного тома.

.. code-block:: console

   /kodik/getChapter?src=  -  название или ссылка на то, что ищем(https://readmanga.io/milye_denki_s_malchikom или Милые деньки с мальчиком) *ОБЯЗАТЕЛЬНЫЙ
                     token=   -  токенский(не токийский!) *ОБЯЗАТЕЛЬНЫЙ
                     by=   -  как ищем(link - через ссылку; name - по имени) *ОБЯЗАТЕЛЬНЫЙ
                     vol=  -  том *ОБЯЗАТЕЛЬНЫЙ
                     ch=   -  глава *ОБЯЗАТЕЛЬНЫЙ
                     
                     
Получаете:

.. code-block:: console

    {
    "code": 200, //int
    "pages": [
        "1": "https://staticrm.rmr.rocks/uploads/pics/01/76/626.jpg",
        "2": "https://staticrm.rmr.rocks/uploads/pics/01/76/626.jpg",
    ],
    "allpages": 2,
    }

    
