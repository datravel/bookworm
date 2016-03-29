# Платежные провайдеры

## Alfa-bank
Ссылки на панель управления:  
https://engine.paymentgate.ru/payment/admin/  
https://engine.paymentgate.ru/mportal/

### Контакты
Контакты службы поддержки:
* ESupport@alfabank.ru - технические вопросы, работа сервиса,
* EMCsupport@alfabank.ru - вопросы по финансовым транзакциям,
* fraudmonitoring@alfabank.ru - fraud-мониторинг.

### Тестовая карта
```
Card: 4111 1111 1111 1111
ExpDate: 12/19
Cardholder: test tes
CVV2: 123
3DS: 12345678
```

## Egopay
Ссылки на панель управления:
* [боевая среда](https://secure.sirena-travel.ru/eGo/auth/index),
* [тестовая среда](https://sandbox.egopay.ru/eGo/auth/index).

### Контакты
Служба поддержки: support@egopay.ru

### Тестовые карты
Тестовая карта для проведения успешной авторизации.
```
Card: 5100 0000 0000 0008
ExpDate: 12/16
Cardholder: Pupkin Vasya
CVV2: 222
```

Тестовая карта, по которой платежный шлюз вернет ошибку авторизации.
```
Card: 4111 1111 1111 1111
ExpDate: 12/16
CardHolder: Pupkin Vasya
CVV2: 222
```

## Uniteller
[Панель управдения](https://lk.uniteller.ru/login/)

### Контакты
Для решения любых вопросов необходимо писать в службу поддержки клиентов (support@uniteller.ru). Для оперативного решения вопросов имеет смысл  также написать Александру Новикову, руководителю проектов электронной коммерции (A.Novikov@uniteller.ru, skype id: alexandr.novikov.uc).

### Тестовые карты
При проведении оплаты по тестовой карте запрос обрабатывается на PROD системе. Поэтому платежи по тестовым картам могут попадать под fraud-фильтры. В этом случае необходимо связываться с Александром Новиковым по скайпу (skype id: alexandr.novikov.uc).

```
Cards:
4000000000002487
4000000000002420
4000000000002438
5000000000002443
5000000000002450

ExpDate: 01/17
Cardholder: UNITELLER TEST
CVV2: 123
```
