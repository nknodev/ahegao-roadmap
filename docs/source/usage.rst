Kodik
=====

.. _/getInfo:

/getInfo
------------

Этот метод достает инфу из API Кодика, Шики и Аниксарта, вроде:

.. code-block:: curl
   /getInfo?src=  -  название или ссылка на то, что ищем
            token=   -  токенский(не токийский!)
            by=   -  как ищем(link - через ссылку; name - по имени)
Получаете

.. code-block:: json
   {
   "title": "Дота2 - топ", // Russian title
   "title_en": "Dota2 - is best", // Eng Title
   "title_orig": "Ymete kudasai", // Original(Japan or Chinese) title
   "pic": "https://static.findanime.net/uploads/pics/01/15/706.jpg", // 


