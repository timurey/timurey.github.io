---
title: Начало работы
date: 2025-01-16 22:25:20
description: 
thumbnail: /introduction/nick-fewings-lirOPuejTbM-unsplash.webp
categories:
- Учебник
tags:
- Введение
- Перевод
- Мешсеть
- Железо
- Софт

author:
  name: timurey
  url: https://t.me/timurey
  source:
    url: https://meshcn.net/introduction/
    author: Hays Chan | 陈希
---

Meshtastic — это автономная коммуникационная платформа, основанная на технологии LoRa. Он обеспечивает связь на больших расстояниях с помощью недорогого и маломощного радиооборудования. Meshtastic предлагает надежное решение для районов, где отсутствует коммуникационная инфраструктура или когда существующие сети вышли из строя. Этот проект полностью поддерживается сообществом и имеет открытый исходный код, подходит как для индивидуальных энтузиастов, так и для профессиональных пользователей.

Следует отметить, что проект Meshtastic все еще находится на экспериментальной стадии, и большинство его прошивок представляют собой бета- или альфа-версии. Это значит, что он еще не идеален, но постоянно совершенствуется. Присоединившись к этому проекту, вы также станете частью его развития.

## Перед началом работ

Прежде чем начать использовать Meshtastic, пожалуйста, посетите и внимательно прочтите официальное руководство по началу работы: [Официальное руководство Meshtastic](https://meshtastic.org/docs/about/).

{% note warning Оязательно: сначала антенна, затем питание %}
Обратите внимание, что антенну необходимо подключить до включения питания, в противном случае усилитель в модеме lora может быть поврежден.
{% endnote %}

### Как настроить свой первый узел Meshtastic?

Для начала вам необходимо установить официальную прошивку Meshtastic. Бета-версии более стабильны, в то же время альфа-версии более передовые, но могут иметь больше проблем. Перед установкой вы можете проверить статус обновления прошивки: [Информация о прошивке](https://pole1.co.uk/firmware/).

После завершения установки вам необходимо будет настроить параметры устройства. Выполнить настройку можно следующими способами:

1. После подключения узла к компьютеру через WiFi или Bluetooth используйте официальный [веб-клиент](https://client.meshtastic.org/) для настройки. Для работы этого интерфейса требуется браузер на базе Chromium (например, Google Chrome, Yandex Browser).
2. Если вы используете мобильный телефон или планшет, вы можете загрузить официальное, либо неофициальное приложение Meshtastic из магазина приложений Android или iOS. При использовании устройства Android или Apple необходимо выполнить сопряжение узла с телефоном через Bluetooth. При этом, сопряжение необходимо проводить через приложение Meshtastic, а не через системный интерфейс операционной системы iOS или Android.

- Приложение Mňoukátko для iOS [ссылка](https://apps.apple.com/ru/app/m%C5%88ouk%C3%A1tko/id6535862998). Поддерживает iOS 17+, macOS 14+.
- Приложение Meshtastic для iOS (недоступно в России): [ссылка](https://apps.apple.com/us/app/meshtastic/id1586432531). Поддерживает iPhone, iPad и Mac.
- Android Meshtastic: [ссылка Google Play](https://play.google.com/store/apps/details?id=com.geeksville.mesh), [ссылка F-Droid](https://f-droid.org/packages/com.geeksville.mesh/)

При настройке необходимо обратить внимание на установку правильного регионального диапазона частот. Например, если вы находитесь в России, выберите регион RU (диапазон частот 868) или EU (диапазон частот 433 МГц). При этом вы можете задавать длинные и короткие имена для узлов. По умолчанию именем узла является MAC-адрес устройства. Большинство других настроек можно оставить по умолчанию, но вы можете задать местоположение устройства или разрешить устройству получать информацию о местоположении от GPS телефона.

Чтобы проверить правильность работы узла, рекомендуется подготовить второй узел во время первоначальной настройки и разместить два узла рядом для проверки связи. Канал связи по умолчанию — «LongFast», а его криптографический ключ — `AQ==`.

## С кем общаться поблизости?

Можете проверить на следующих картах наличие поблизости уже действующих узлов:
- [https://meshtastic.taubetele.com/](https://meshtastic.taubetele.com/)
- [https://meshsense.affirmatech.com/](https://meshsense.affirmatech.com/)
- [https://meshmap.net/](https://meshmap.net/)
- [https://meshtastic.liamcottle.net/](https://meshtastic.liamcottle.net/)
- [https://tracker.bircom.in/](https://tracker.bircom.in/)

Нужно понимать, что на картах могут быть отмечены не все действующие узлы. 

## Как выбрать место установки узла?

При установке узлов важно выбрать место на большей высоте. Большая высота может значительно улучшить покрытие сигнала и стабильность связи. Попробуйте разместить узлы на крыше высокого здания или на вершине горы.

Что касается настроек ролей, в большинстве случаев вам следует выбрать роль "CLIENT" если вы находитесь в движущемся транспортном средстве, таком как автомобиль, самолет или корабль, вам следует выбрать роль "CLIENT_MUTE" только в очень редких случаях случаи, когда "ROUTER" следует выбирать только тогда, когда вы находитесь в самой высокой точке в радиусе нескольких десятков километров. Подробнее можно почитать на официальном [сайте](https://meshtastic.org/docs/configuration/tips/)

Если вы хотите узнать больше о конкретных функциях и использовании ролей узлов, вы можете обратиться к ["Подробный разбор ролей в Meshtastic: когда использовать CLIENT, ROUTER и REPEATER"](/how-to-choose-roles/).

## Советы по улучшению дальности связи

Частотный диапазон 868 МГц, используемый Meshtastic, имеет относительно низкую мощность, а дальность связи, как правило, ограничивается прямой видимостью. Линия прямой видимости — это диапазон горизонта, видимый с места расположения антенны устройства, при этом распространение сигнала может быть ограничено препятствиями, такими как здания, деревья и холмы. На уровне моря дальность видимости человека среднего роста составляет около 4,5 км. Если вы стоите на горе или высоком здании, зона покрытия сигнала может быть дальше.

Точное расстояние прямой видимости можно оценить с помощью этого инструмента: [Калькулятор прямой видимости](https://pole1.co.uk/dth/).

Высота антенны оказывает существенное влияние на качество сигнала. В общем случае, при увеличении высоты антенны на один метр дальность прямой видимости может увеличиться примерно на один километр. Вот почему коммерческие радиовышки обычно строятся высоко и проектируются очень высокими.

## Выбор и установка антенны

В густонаселенных районах может быть достаточно использовать небольшую антенну, входящую в комплект устройства. Однако в районах с небольшим количеством пользователей или со сложным рельефом вам может потребоваться приобрести более эффективную антенну. Частотный диапазон антенны должен соответствовать району расположения устройства. Например, диапазон частот в Китае составляет 470 МГц, поэтому антенна должна быть рассчитана на этот диапазон частот. При покупке антенны рекомендуется выбирать известный бренд и приобретать ее через официальные каналы, чтобы избежать покупки некачественной продукции.

Антенну следует устанавливать как можно выше, желательно на открытом пространстве снаружи здания. При установке антенны убедитесь, что она расположена вертикально. Если вам необходимо увеличить расстояние между антенной и устройством, выберите высококачественный коаксиальный кабель, например LMR400, и сделайте длину кабеля как можно короче, чтобы уменьшить потери сигнала.

## Важность поддержания круглосуточной работы вашего узла

Сеть Meshtastic основана на ретрансляции сообщений. Если узел отключается, канал связи прерывается, поэтому рекомендуется всегда поддерживать работу узлов 24 часа в сутки. Чем больше узлов, тем выше устойчивость и покрытие сети.

## Рекомендации по MQTT

MQTT — встроенная функция Meshtastic, подключающая узлы к локальному Интернету через Ethernet или WiFi. Для полностью изолированных пользователей это способ получить больше узловых соединений. Однако при включении MQTT вы потенциально транслируете весь трафик своей сети в общедоступный Интернет, включая сообщения и информацию о местоположении. Поэтому рекомендуется включать эту функцию с осторожностью, в соответствии с реальными потребностями.

В настоящее время в Китае сравнительно мало пользователей Meshtastic (примерно менее 100 человек). В этом случае, чтобы новичкам было удобнее пользоваться приложением, вы можете временно включить функцию MQTT. Это поможет новым пользователям быстрее получать ответы, не тратя время на длительное ожидание из-за отсутствия поблизости других узлов LoRa.

<!-- ## Влияние особых метеорологических условий на сигналы

При определенных атмосферных условиях сигнал может отражаться обратно на землю, обеспечивая покрытие за пределами прямой видимости. Например, когда высокое давление вызывает температурную инверсию, это может создать эффект тропосферного волновода, заставляя радиоволны отражаться в атмосфере. Это явление может значительно увеличить расстояние, на которое может распространяться сигнал. -->
