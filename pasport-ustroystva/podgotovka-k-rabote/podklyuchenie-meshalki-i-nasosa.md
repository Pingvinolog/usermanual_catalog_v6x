---
order: 4
title: Подключение мешалки и насоса
---

Рассмотрим основные способы подключения мешалки и насосов к блоку автоматики

### Подключение через силовые контакты К2 и К3 (напрямую)

Данный способ подключения подходит, если вы подключаете двигатель без высокого пускового тока или на плате были установлены усиленные симисторы.



**Вот тут подробнее про это все**



Параметр P40 отвечает за функцию автоматического запуска при подаче питания (Power Start Operation). Вот как его можно использовать:

1. Возможные значения:

-  00: Автоматический запуск разрешен

-  01: Автоматический запуск запрещен

1. Для включения автоматического старта:

-  Установите P40 = 00

-  При этом инвертор будет автоматически запускаться при подаче питания

1. Для отключения автоматического старта:

-  Установите P40 = 01

-  Инвертор будет ожидать ручного запуска после подачи питания

***Важные замечания***: не рекомендуем использовать автостарт по соображениям безопасности. Данный режим может произвести случайный запуск двигателя и повредить оборудование.

### Подключение через силовые контакты К2 и К3 (через контактор)

Подключение и настройка преобразователя происходи аналогично прямого подключения, за исключением промежуточного силового реле, через который происходит подключение питания к преобразователю.

### Подключение через ПЧ1/ПЧ2

На платах **версии 7 и выше** появился специализированный разъем для управления частотными преобразователями или силовыми реле. Разъем находится слева от разъёмов клапанов.

#### Пример подключения

Hазберем подключение мешалки через разъем ПЧ1/ПЧ2 и частотный преобразователь на примере примере частотного преобразователя Suswe T13-750W-12-H. Для других производителей и моделей подключение описывается в инструкции к конкретному устройству.

Настройка преобразователя:

1. Преобразователь подключается к сети и двигателю согласно инструкции с разъемы W V U N LP

2. Подключите двух жильный провод к разъёму ПЧ1/ПЧ2 на контакты 1 и 3. Контакт 1 сухого контакта к клемме X0, а контакт 3 к клемме GND (земля) на частотного преобразователя.

3. Настройте источник сигнала пуска/останова:

-  В меню P01 установите значение 01 (управление от внешнего терминала)

-  P02: выберите режим останова (рекомендуется 01 - торможение с замедлением)

-  В меню P28 установите значение 0 для X0 (X0: вперед/стоп)

-  В меню P29 установите значение 0 (без функции для X1)

Через меню “Проверка оборудования“ проверьте запуск и остановку двигателя мешалки

Через разъем ПЧ1/ПЧ2 можно одновременно управлять двумя частотными преобразователями. Контакт 1 и 3 разъема ПЧ1/ПЧ2 в программе будет обозначаться как “**Мешалка**”, а контакты 2 и 3 как “**Насос**”.

\*\*\*Примечание: \*\*\*частотный преобразователь источник сильного электромагнитного излучения, которое может влиять на работу датчиков температуры и работу блока автоматики. Если происходят скачки температуры во время включения и выключения преобразователя, то установите на силовой кабель преобразователя ферритовое кольцо или отнесите блок преобразователя как можно дальше от датчиков температуры и блока автоматики.