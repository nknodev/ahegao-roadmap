/kodik
=====

.. _/getInfo:

/getInfo
------------

Этот метод достает инфу из API Кодика, Шики и Аниксарта, вроде:

.. code-block:: console

   /getInfo?src=  -  название или ссылка на то, что ищем *ОБЯЗАТЕЛЬНЫЙ
            token=   -  токенский(не токийский!) *ОБЯЗАТЕЛЬНЫЙ
            by=   -  как ищем(link - через ссылку; name - по имени) *ОБЯЗАТЕЛЬНЫЙ
Получаете

.. code-block:: console

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
   "statusAPI": 200, //int
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
