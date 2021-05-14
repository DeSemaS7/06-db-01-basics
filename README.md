###### Задача 1

**-Электронные чеки в json виде.** 
<br>NoSQL, например Mongo. отличный выбор для документо-ориентированных данных.


**-Склады и автомобильные дороги для логистической компании**
<br>не понял что должно быть в базе. если просто справочник с адресами, то вероятно NoSQL. 
если же привязка к координатам, то я бы использовал SQL и тип данных geography 

**-Генеалогические деревья**
<br>графовая NoSQL.

**-Кэш идентификаторов клиентов с ограниченным временем жизни для движка аутентификации**
<br>Memcached/Redis. не нужна структура, ttl, большая скорость.

**-Отношения клиент-покупка для интернет-магазина**
<br>MongoDB


###### Задача 2

**Данные записываются на все узлы с задержкой до часа (асинхронная запись)**
<br>CAP: AP
<br>PACELC: PA/EL


**При сетевых сбоях, система может разделиться на 2 раздельных кластера**
<br>CAP: AC 
<br>PACELC: PA/EC

**Система может не прислать корректный ответ или сбросить соединение**
<br>CAP: CP
<br>PACELC: PC/EC

###### Задача 3
не могут. они противоречат друг другу. 
хотя если рассматривать систему как некий комплекс бд, то вполне вероятно что будут использоваться оба подхода в решении общей задачи.

###### Задача 4

Pub/Sub подразумевает под собой наличие подписчика и издателя. 
издатель формирует и публикует в системе сообщения с каким-то временем жизни. 
подписчик забирает нужные сообщения себе по какому-то фильтру и обрабатывает.

<br>к минусам можно отнести асинхронность поступления данных от издателя к подписчикам, т.к. у одного издателя может быть множество подписчиков, что приведёт к созданию очередей. (либо же у одного подписчика несколько источников-издателей, что так же приведёт к очередям)
