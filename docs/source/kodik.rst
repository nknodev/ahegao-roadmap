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
    "code": 200 // int
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
               tags: [
                  "romantic": true,
                  "comedy": true,
                  // ...
               ],
               casts: [
                  "anilibria",
                  "anidub",
               ],
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
   



.. _/getVideo:

/getVideo
------------
.. note:: 

   Класс доступен для владельцев премиум-токенов.
   
Этот класс очень важен для пользователей API, так как он предоставляет возможность получать декодированный mp4 файл из плеера Kodik, как описано в :ref:`/getVideoLink`, кодик передает файлы для возпроизведения в закодированном виде(Кстати, так делает не только кодик), но сам плеер возпроиводит blob-файлы, получается используя метод :ref:`/getVideoLink` и hls.js, вы можете возпроизводить видео из кодика в сторонних плеерах, поддерживающих blob.

Передаете

.. code-block:: console
   
   /getVideo?link=//aniqit.com/serial/40506/bdba0731cc10b9f6169dba1bea31886a/720p
             token=1234567890


.. note:: 

   Нужно передавать ссылку на серию, а не на сериал

Получаете

.. code-block:: console
      
      {
   
      "360":[{"src":"//cloud.kodik-storage.com/useruploads/70d17edb-6bd8-41e7-aefd-fea8edb6c72a/642bbfc75ab8535e480757c9eef7d2e5:2022020907/360.mp4"],
      "480":[{"src":"//cloud.kodik-storage.com/useruploads/70d17edb-6bd8-41e7-aefd-fea8edb6c72a/642bbfc75ab8535e480757c9eef7d2e5:2022020907/480.mp4"}],
      "720":[{"src":"//cloud.kodik-storage.com/useruploads/70d17edb-6bd8-41e7-aefd-fea8edb6c72a/642bbfc75ab8535e480757c9eef7d2e5:2022020907/720.mp4"}],
      "apistatus": 200
   
      }


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


