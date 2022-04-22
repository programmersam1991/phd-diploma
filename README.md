# Курсовая работа курса «Аппаратное обеспечение (Hardware)»

### Цель курсовой работы:

Целью проекта является создание аппаратной конфигурации проекта АСУ ТП линии хранения углекислоты. 

В результате выполнения этого задания вы:
1. Научитесь подбирать устройства для АСУ ТП на сайтах ведущих производителей.
1. Разработайте полноценную спецификацию на закупку по основным видам оборудования, необходимым при проектировании АСУ ТП (датчики, регуляторы, исполнительные механизмы).
1. Создадите проект аппаратной конфигурации для АСУ ТП.

-----

### Чек-лист готовности к курсовой работе:

1. Ознакомьтесь с сайтами ведущих производителей, на которых необходимо будет подобрать оборудование для новой АСУ ТП. 

Список производителей:
- датчики: [IFM](https://www.ifm.com/ru/ru), [BALLUFF](https://www.balluff.com/ru-ru), [OMRON](https://industrial.omron.ru/ru/home), [ОВЕН](https://owen.ru/)
- элементы автоматики: [SCHNEIDER ELECTRIC](https://www.se.com/ru/ru/)
- ПЛК, модули ввода/вывода, периферийные и интерфейсные модули, частотные преобразователи, регулирующие клапаны: [SIEMENS](https://mall.industry.siemens.com/goos/WelcomePage.aspx?regionUrl=/ru&language=ru)
- частотные преобразователи, регулирующие клапаны: [DANFOSS](https://www.danfoss.com/ru-ru/)

2. Зарегистрируйтесь на [портале Siemens](https://mall.industry.siemens.com/goos/WelcomePage.aspx?regionUrl=/ru&language=ru) и получите персональный логин и пароль для входа в систему.
3. Загрузите и установите программное обеспечение для создания HMI WinCC, входящее в состав пакета TIA Portal с [официального сайта Siemens](). После установки вы получите бесплатную полнофункциональную версию trial-версию на 21 день.

-----

### Инструкция к выполнению курсовой работы:

1. В соответствии со [структурной схемой]() и техническим заданием подберите датчики на сайтах производителей, указанных выше.
2. Расставьте подобранные датчики на [структурной схеме]() в соответствии с заданным технологическим процессом, указанным в техническом задании.
3. Аналогичным образом подберите регуляторы и исполнительные механизмы (при необходимости).
4. Расставьте подобранные регуляторы и исполнительные механизмы на схеме в соответствии с техническим заданием.
5. Разработайте HMI-проект для АСУ ТП в соответствии с входными данными об аппаратном обеспечении.

[Шаблон выполнения задания]()

**Техническое задание**

Разрабатываемый проект содержит следующие структурные элементы:

1. Ёмкости для хранения углекислоты TANK1...TANK3 - 3 шт.
2. Волноводный радарный уровнемер для измерения уровня в ёмкостях LM1...LM3 - 3 шт.
3. Датчик давления углекислоты в ёмкости PM1...PM3- 3 шт.
4. Клапан ввода углекислоты в ёмкости VIL1..VIL3 - 3 шт.
5. Клапан выхода углекислоты к потребителю VOL1...VOL3 - 3 шт.
6. Основной вводной клапан VMI1 - 1 шт.
7. Основной выходной клапан VMO1 - 1 шт.
8. Регулирующий клапан для отдачи углекислоты потребителю, управляемый сервоприводом VRO1 - 1 шт.
9. Регулирующий клапан для ограничения потока углекислоты в ёмкости, управляемый сервоприводом VRI1 - 1 шт.
10. Струйный расходомер для подсчёта мгновенного и накопительного расхода углекислоты в ёмкостях CMI1 -1 шт.
11. Электромагнитный расходомер выходного потока углекислоты CML1 - 1 шт.
12. Датчик температуры углекислоты в ёмкостях (термометр сопротивления типа Pt100) T1...T3 - 3 шт.
13. Основной углекислотный насос мощностью 3 кВт ME1 - 1 шт.
14. Резервный углекислотный насос мощностью 3 кВт AE1 - 1 шт.
15. Частотный преобразователь управления вращением насосов углекислоты FC1, FC2 - 2 шт.
16. HMI-панель HMI1 - 1 шт.
17. Промышленный логический контроллер PLC1 - 1 шт.

Чтобы иметь более широкое представление о необходимой АСУ ТП, изучите [структурную схему]().

*Алгоритм работы:*

1. Ёмкости предназначены для хранения углекислоты с участка по производству.
2. Волноводные датчики LM1...LM5 предназначены для измерения уровня в ёмкостях. Датчики установлены на каждой ёмкости.
3. Основной углекислотный насос поддерживает давление и уровень в ёмкостях. Насос управляется с помощью частотного преобразователя FC1. Скорость наполнения поддерживается с помощью вводного регулирующего клапана VRI1, расход отдачи потребителю - с помощью регулирующего клапана VRO1.
4. Резервный углекислотный насос включается в случае неисправности основного углекислотного насоса. Насос управляется с помощью частотного преобразователя FC2.
5. Датчики давления углекислоты PM1...PM3 устанавливаются через соединительный штуцер на дне ёмкости и измеряют давление углекислоты. Датчики необходимы для задания параметров управления углекислотного насоса.
6. Основной вводный клапан VMI1 устанавливается после насоса углекислоты и служит для перекрытия трубопровода и, соответственно, подачи углекислоты в ёмкости.
7. Основной выходной клапан VMO1 перекрывает подачу углекислоты потребителю.
8. Расходомер CMI1 подсчитывает пропущенный через сечение трубопровода расход углекислоты и подсчитывает общий объем произведенной углекислоты с помощью сравнения значения с выходным значением на расходомере CML1.
9. Датчики температуры T1...T3 измеряют теипературу углекислоты и выводят её на экран панели HMI.

*Требования к содержанию HMI-проекту*

1. ОСНОВНОЙ ЭКРАН - структурная схема, расположение всех датчиков и их мгновенные значения.
2. ЭКРАН ОШИБОК - вывод основных ошибок.
3. ЭКРАН ПАРАМЕТРИРОВАНИЯ - изменение пороговых значений давления, температуры, угла открытия регулирующих клапанов и т.д.
4. ЭКРАН ГРАФИКОВ - отображение записанных значений показаний датчиков на координатной плоскости. 

-----

### Правила приема работы:

1. Курсовая работа должна быть реализована локально и опубликована на сервисе [GitHub Pages](https://pages.github.com/)
2. Отправлена ссылка на документ (Google Doc) с выполненным заданием в личном кабинете
3. Документ размещен на личном Google Disk
4. К документу настроены права доступа «Просматривать могут все в Интернете, у кого есть ссылка»

-----

### Критерии оценки:

Зачёт по разработанному проекту может быть получен, если работа соответствует следующим критериям:

1. Оборудование подобрано корректно по необходимым параметрам.
2. HMI-проект размечен в соответствии с составом системы.
