**1. https://github.com/FisanovE/Ticket-parse8**
Напишите программу на языке программирования java, которая прочитает файл `tickets.json` и рассчитает:
- Минимальное время полета между городами Владивосток и Тель-Авив для каждого авиаперевозчика
- Разницу между средней ценой  и медианой для полета между городами  Владивосток и Тель-Авив

Программа должна вызываться из командной строки Linux, результаты должны быть представлены в текстовом виде. 
В качестве результата нужно прислать ответы на поставленные вопросы и ссылку на исходный код.

<details>

<summary>tickets.json</summary>

```json
{
  "tickets": [{
    "origin": "VVO",
    "origin_name": "Владивосток",
    "destination": "TLV",
    "destination_name": "Тель-Авив",
    "departure_date": "12.05.18",
    "departure_time": "16:20",
    "arrival_date": "12.05.18",
    "arrival_time": "22:10",
    "carrier": "TK",
    "stops": 3,
    "price": 12400
  }, {
    "origin": "VVO",
    "origin_name": "Владивосток",
    "destination": "TLV",
    "destination_name": "Тель-Авив",
    "departure_date": "12.05.18",
    "departure_time": "17:20",
    "arrival_date": "12.05.18",
    "arrival_time": "23:50",
    "carrier": "S7",
    "stops": 1,
    "price": 13100
  }, {
    "origin": "VVO",
    "origin_name": "Владивосток",
    "destination": "TLV",
    "destination_name": "Тель-Авив",
    "departure_date": "12.05.18",
    "departure_time": "12:10",
    "arrival_date": "12.05.18",
    "arrival_time": "18:10",
    "carrier": "SU",
    "stops": 0,
    "price": 15300
  }, {
    "origin": "VVO",
    "origin_name": "Владивосток",
    "destination": "TLV",
    "destination_name": "Тель-Авив",
    "departure_date": "12.05.18",
    "departure_time": "17:00",
    "arrival_date": "12.05.18",
    "arrival_time": "23:30",
    "carrier": "TK",
    "stops": 2,
    "price": 11000
  }, {
    "origin": "VVO",
    "origin_name": "Владивосток",
    "destination": "TLV",
    "destination_name": "Тель-Авив",
    "departure_date": "12.05.18",
    "departure_time": "12:10",
    "arrival_date": "12.05.18",
    "arrival_time": "20:15",
    "carrier": "BA",
    "stops": 3,
    "price": 13400
  }, {
    "origin": "VVO",
    "origin_name": "Владивосток",
    "destination": "TLV",
    "destination_name": "Тель-Авив",
    "departure_date": "12.05.18",
    "departure_time": "9:40",
    "arrival_date": "12.05.18",
    "arrival_time": "19:25",
    "carrier": "SU",
    "stops": 3,
    "price": 12450
  }, {
    "origin": "VVO",
    "origin_name": "Владивосток",
    "destination": "TLV",
    "destination_name": "Тель-Авив",
    "departure_date": "12.05.18",
    "departure_time": "17:10",
    "arrival_date": "12.05.18",
    "arrival_time": "23:45",
    "carrier": "TK",
    "stops": 1,
    "price": 13600
  },
    {
      "origin": "VVO",
      "origin_name": "Владивосток",
      "destination": "UFA",
      "destination_name": "Уфа",
      "departure_date": "12.05.18",
      "departure_time": "15:15",
      "arrival_date": "12.05.18",
      "arrival_time": "17:45",
      "carrier": "TK",
      "stops": 1,
      "price": 33400
    },
    {
      "origin": "VVO",
      "origin_name": "Владивосток",
      "destination": "TLV",
      "destination_name": "Тель-Авив",
      "departure_date": "12.05.18",
      "departure_time": "6:10",
      "arrival_date": "12.05.18",
      "arrival_time": "15:25",
      "carrier": "TK",
      "stops": 0,
      "price": 14250
    },
    {
      "origin": "LRN",
      "origin_name": "Ларнака",
      "destination": "TLV",
      "destination_name": "Тель-Авив",
      "departure_date": "12.05.18",
      "departure_time": "12:50",
      "arrival_date": "12.05.18",
      "arrival_time": "14:30",
      "carrier": "SU",
      "stops": 1,
      "price": 7000
    },
    {
      "origin": "VVO",
      "origin_name": "Владивосток",
      "destination": "TLV",
      "destination_name": "Тель-Авив",
      "departure_date": "12.05.18",
      "departure_time": "16:50",
      "arrival_date": "12.05.18",
      "arrival_time": "23:35",
      "carrier": "SU",
      "stops": 1,
      "price": 16700
    },
    {
      "origin": "VVO",
      "origin_name": "Владивосток",
      "destination": "TLV",
      "destination_name": "Тель-Авив",
      "departure_date": "12.05.18",
      "departure_time": "6:10",
      "arrival_date": "12.05.18",
      "arrival_time": "16:15",
      "carrier": "S7",
      "stops": 0,
      "price": 17400
    }]
}
```
</details>

***

**2. https://github.com/FisanovE/Wallet**
Напишите приложение, которое по REST принимает запрос вида:   `POST api/v1/wallet`:

<details>
<summary>json</summary>
  
```json
{
"walletId": "UUID",
"operationType": "DEPOSIT" or "WITHDRAW",
"amount": 1000
}
```
</details>
после выполняет логику по изменению счета в базе данных. Также есть возможность получить баланс кошелька:  `GET api/v1/wallets/{WALLET_UUID}` 
Должны быть написаны миграции для базы данных с помощью liquibase. Обратите особое внимание проблемам при работе в конкурентной среде (1000 RPS по одному кошельку). Ни один запрос не должен быть не обработан (50Х error). Предусмотрите соблюдение формата ответа для заведомо неверных запросов, когда кошелька не существует, не валидный json, или недостаточно средств. приложение должно запускаться в докер контейнере, база данных тоже, вся система должна подниматься с помощью docker-compose. Предусмотрите возможность настраивать различные параметры как на стороне приложения так и базы данных без пересборки контейнеров. Эндпоинты должны быть покрыты тестами.

Стек:
java 8-17 Spring 3 Postgresql

***
**3. https://github.com/FisanovE/HonestSign**

Необходимо реализовать на языке Java (можно использовать 17 версию) класс для работы с API Честного знака. Класс должен быть thread-safe и поддерживать ограничение на количество запросов к API. Ограничение указывается в конструкторе в виде количества запросов в определенный интервал времени. Например:
```java
public CrptApi(TimeUnit timeUnit, int requestLimit)
```
`timeUnit` – указывает промежуток времени – секунда, минута и пр.  
`requestLimit` – положительное значение, которое определяет максимальное количество запросов в этом промежутке времени.

**При превышении лимита запрос вызов должен блокироваться, чтобы не превысить максимальное количество запросов к API и продолжить выполнение, без выбрасывания исключения, когда ограничение на количество вызов API не будет превышено в результате этого вызова. В любой ситуации превышать лимит на количество запросов запрещено для метода.**

Реализовать нужно единственный метод – Создание документа для ввода в оборот товара, произведенного в РФ. Документ и подпись должны передаваться в метод в виде Java объекта и строки соответственно.

Вызывается по HTTPS метод POST следующий URL:  
https://ismp.crpt.ru/api/v3/lk/documents/create

В теле запроса передается в формате JSON документ:

<details>
<summary>json</summary>
```json
{
    "description": {
        "participantInn": "string"
    },
    "doc_id": "string",
    "doc_status": "string",
    "doc_type": "LP_INTRODUCE_GOODS",
    "importRequest": true,
    "owner_inn": "string",
    "participant_inn": "string",
    "producer_inn": "string",
    "production_date": "2020-01-23",
    "production_type": "string",
    "products": [
        {
            "certificate_document": "string",
            "certificate_document_date": "2020-01-23",
            "certificate_document_number": "string",
            "owner_inn": "string",
            "producer_inn": "string",
            "production_date": "2020-01-23",
            "tnved_code": "string",
            "uit_code": "string",
            "uitu_code": "string"
        }
    ],
    "reg_date": "2020-01-23",
    "reg_number": "string"
}
```
</details>

При реализации можно использовать библиотеки HTTP клиента, JSON-сериализации. Реализация должна быть максимально удобной для последующего расширения функционала.
Решение должно быть оформлено в виде одного файла **CrptApi.java**. Все дополнительные классы, которые используются должны быть внутренними.
Можно прислать ссылку на файл в GitHub.
В задании необходимо просто сделать вызов указанного метода, реальный API не должен интересовать. 

***  

**4. https://github.com/FisanovE/agregator**

Необходимо реализовать проект на Spring Boot 3.x, в котором необходимо реализовать REST-сервис.  
Сервис должен отвечать на единственный запрос о погоде на неделю и курс валюты, например, рубля к евро и доллару.  
Чтобы получить прогноз погоды и курс валюты необходимо обратиться к внешним REST-сервисам (openweathermap.org и currate.ru), потом необходимо собрать аггрегированный ответ и отправить.

Получается:
на входе: любой день и валюта, к которой нужно найти курс рубля
на выходе: прогноз погоды на всю неделю, в которой этот день + текущий курс указанной в запросе валюты

Код необходимо покрыть тестами: unit и интеграционными. Для unit-тестирования необходимо использовать Mockito, для интеграционного REST Assured.

Рекомендации к выполнению:
Задача должна быть решена и реализованы требуемые функции, будут приветствоваться следующие вещи:
1.     Код оформлен в соответствии Java Code Conventions или более поздними известными стандартами оформления кода для Java
2.     Имеется инструкция по запуску/сборке проекта, достаточно ее сделать в файле README.md
3.     Сложные места в коде прокомментированы
4.     Код покрыт юнит-тестами
5.     Хорошо бы использовать Gradle в качестве инструмента для сборки

Дополнительно:
1.     Используя Open API описать сервис YAML файлом и предоставить его.
2.     Предоставить небольшую коллекцию на Postman.


***  

**4. https://github.com/FisanovE/stub**

Разработать заглушку на Java (Spring), которая обеспечивает обработку http-запросов и запись сообщений в Kafka.

1.Заглушка должна обрабатывать запросы с маршрутом /post-message и методом запроса POST;  

2.Тело запроса должно содержать json, в котором присутствует всего одно поле msg_id. Пример запроса к заглушке:
```json
{
"msg_id": "1234567890"
}
```
3.Получив запрос POST /post-message, заглушка должна достать из тела запроса msg_id и на его основе сформировать сообщение, которое затем отправится в кафку в топик «postedmessages»;  

4.В сообщении в кафку:
- текущее время (сохранить unix timestamp в момент получения запроса),
- маршрут запроса,
- метод запроса
- msg_id

Пример сообщения в топик Kafka:

```json
{ 
"msg_id": "1234567890",
"timestamp": "1694171306000",
"method": "POST",
"uri": "/post-message"
}
```

5.В ответ на запрос заглушка возвращает «200 ОК» если записала;  
если в процессе работы возникла ошибка и сообщение не дошло до кафки – возвращаем ошибку 500;  
Для выполнения задания понадобится вручную поднять локально Kafka и Zookeeper.  

**Примечание:** Чтобы просмотреть очередь сообщений в кафке, можно воспользоваться Kafka Tool.
