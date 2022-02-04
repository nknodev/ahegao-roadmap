/kodik
=====

.. _/getVideoInfo:

/getVideoInfo
------------

Этот метод достает инфу из API Кодика, Шики и Аниксарта, вроде:

.. code-block:: console

   /kodik/getInfo?src=  -  название или ссылка на то, что ищем *ОБЯЗАТЕЛЬНЫЙ
                token=   -  токенский(не токийский!) *ОБЯЗАТЕЛЬНЫЙ
                by=   -  как ищем(link - через ссылку; name - по имени) *ОБЯЗАТЕЛЬНЫЙ
Вывод:

.. code-block:: console

    {
    "code": 0 // int
    "object":
               {
               "title": "Дота2 - топ", // Название на русском
               "title_en": "Dota2 - is best", // Название на английском
               "title_orig": "Ymete kudasai", // Оригинальное(на Японском или Китайском) название
               "pic": "https://static.findanime.net/uploads/pics/01/15/706.jpg", // Картинка(не превью)
               "shiki": "https://shikimori.one/...", // ссылка на шики
               "releaseyear": 2017, // Год релиза(тип int)
               "releasestatus": "ongoing", // Статус выхода: ongoing - выходит сейчас; released - вышел; announce - анонс.
               "eps": 12, // Эпизодов(тип int)
               "score": 4.12, // Оценки, указываются до 5(тип float)
               "mangaauthor": "Dagiwara Daisuke", // Автор манги(инфа с шики)
               "director":  "Kana Fujiwara", // Режиссер
               tags: [ //
                  "romantic": true, // boolean
                  "comedy": true,  // boolean
                  // ...
               ],
               casts: [
                  "anilibria": true, // boolean
                  "anidub": false,  // boolean
                    ]
               }
    }
   


.. _/getVideoLink:

/getVideoLink
------------
Передаете

.. code-block:: console

   /getVideoLink?src=  -  Ссылыч на плеер *ОБЯЗАТЕЛЬНЫЙ
                 token=   -  токенский *ОБЯЗАТЕЛЬНЫЙ
                 
Получаете

.. code-block:: console

   {
   "link": "blob:https://aniqit.com/..."
   }
   
.. note:: 
   
   К вашему вниманию: у нас нет возможности декодировать blob-ы, так как они довольно непросто устроены, если вы используете JS в своем проекте можете использовать `это`_
.. _это: https://stackoverflow.com/questions/14952052/convert-blob-url-to-normal-url


.. _/getVideo:

/getVideo
------------

.. note:: 

   Данный метод не проходил тестирования, а значит он будет недоступен в ближайшей финальной версии API. Надеемся, что он скоро появится
   
Этот класс очень важен для пользователей API, так как он предоставляет возможность получать декодированный mp4 файл из плеера Kodik, как описано в :ref:`/getVideoLink`, кодик передает файлы для возпроизведения в закодированном виде(Кстати, так делает не только кодик), но сам плеер возпроиводит blob-файлы, получается используя метод :ref:`/getVideoLink` и hls.js, вы можете возпроизводить видео из кодика в сторонних плеерах, поддерживающих blob.





.. _/counter:

/counter
------------

Счетчик релизов из базы Kodik.

.. code-block:: console


   {
   "anime-serials": 11367,
   "anime-films": 1245,
   "allanimes": 12612,
   }


