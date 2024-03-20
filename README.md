Темы разобранные в статьях (в самом низу есть групировка пунктов статей по темам)

1. Определение размера выборки(срока) из мощности и MDE
2. Сплит-система
3. Репрезентативность выборки, стратификация
4. Проверка метода с помощью FPR в A/A, или по мощности+FPR в A/A/B на искуственных данных
5. Методы расчета А/B тестов, методы повышения мощности:
пуассон-бутстрап, бакетизация, delta-метод, CUPED, постнормировка, парная стратификация
6. Сравнение методов
7. Проблема подглядывания и методы досрочного прекращения теста
8. Расчет срока теста по старым или предэксп. данным
9. Выводы из результатов теста
____
_________
Основные шаги
https://education.yandex.ru/journal/kak-provesti-a-b-testirovanie-6-prostykh-shagov
____
Тинькофф - поступашки
https://youtu.be/oa8j8TOndpE

1. подготовка к АБ
2. размер выборки/время теста
3. сплит-система
4. репрезентативность выборки
5. калькулятор АБ тестов
6. мощность
7. Z/Т-тесты
8. множественные сравнения
9. повторение ключевого из лекции
____
Мифы аб-тестов
https://www.youtube.com/watch?v=IFAaTKVKH1A

1. Контекст - много метрик, большой трафик
2. Метрики - степень агрегации vs чувствительность к покрасу
3. Ратио > расчет квантилей
4. Т-тест для ратио (дельта метод)
5. Бакет vs пуассон-бутстрап - биг дата
6. Повышение мощности - 4 способа кратко
7. Подготовка - размер выборки по MDE
8. Течение теста - подглядывания, мониторинг MDE
9. Принятие решения - подглядывания, отчет стат зн рез-та - аплифт>дов инт
____   
ВК
https://vkteam.medium.com/practitioners-guide-to-statistical-tests-ed2d580ef04f
1. (1.2) FPR и мощность - ошибки 1 рода vs 2-го 1.3. Распределения искусственных данных (есть аплифт)
1. (1.4-1.5) FPR контролирует порог alpha - равномерное p-val в A/A
2. (2.1) Как выбрать тест? - Сравниваем FPR и мощности разных тестов на искусственных данных
2. clicks: 1Т-тест 2Mann-Whitney
3. globalCTR: 1binom-Z 2Bootstrap 3Delta-method 4Bucketization 5Linearization ...... дальше не читал
____
Авито 1
https://habr.com/ru/company/avito/blog/571094/
1. Гипотезы АБ,
дов.инт и относ.метрики - более понятные резы для заказчиков
2. Проверка метода FPR A/A (снова)
(сначала на искусственных, затем на реальных)
3. Относительный T-тест - дельта метод
4. О чём говорят серые метрики.
инсайты из стат. незнач. - если эффект необнаружен то он в пределах дов.инт.
5. Выбросы в A/B - уменьшение дисперсии -увеличение мощности
как не делаем:
MW, логарифмирование метрики, выкинуть выбросы
Выкинуть выбросы в предэксп. период можно
____
Авито 2
https://habr.com/ru/company/avito/blog/571096/
Методы повышения мощности (mentioned in мифы, теперь подробно)

1. a Увеличение срока бесполезно, b определение срока в предэксп. период
2. CUPED, постнормировка(исп-ет бутстрап)
3. Стратификация - метод разбивки на Тест и Контроль
4. Парная стратификация - учет ковар. между Т и С
5. Сравнение всех методов и их комбинаций с парной страт.
____   
Карпов - размер выборки
https://www.youtube.com/watch?v=2nP\_gcut7SU
1. Расчет размера выборки из мощности на примере Z-теста
2. Формулы для Т-теста
https://towardsdatascience.com/required-sample-size-for-a-b-testing-6f6608dd330a
____
Карпов - подглядывания
https://www.youtube.com/watch?v=jnFVmtaeSA0
1. А/А с подглядываниями - примеры - FPR>5%
2. Нельзя добирать выборку для подгона
3. Срок заранее, решение в конце - фиксируем FPR
____
Учи.ру
https://habr.com/ru/company/uchi_ru/blog/500918/
1. Множественные сравнения - много срезов/разных метрик/тритментов - Бонферони
2. Подглядывания - FPR > 5%
3. Покок и О-Браян-Флеминг (+Optimizely)
4. Расчет срока из MDE по старым данным используя Покока и Бонферони
____
____
Что стоит еще прочитать?
Другие курсы карпова на https://s1.sharewood.co/

https://medium.com/statistics-experiments/%D0%BA%D0%BE%D0%B3%D0%B4%D0%B0-%D0%BE%D1%81%D1%82%D0%B0%D0%BD%D0%B0%D0%B2%D0%BB%D0%B8%D0%B2%D0%B0%D1%82%D1%8C-a-b-%D1%82%D0%B5%D1%81%D1%82-%D1%87%D0%B0%D1%81%D1%82%D1%8C-1-mde-7d39b668b488
1. мониторинг MDE - пока не найден эффект, найденый будет меньше current MDE(упомянуто в мифах 8)
2. он сравнивает MDE с аплифтом, но есть мнение что это туфта:
https://habr.com/ru/companies/lamoda/articles/728034/
____
____
Групировка пунктов статей по тематике:

0. Т-тест для отношения, дельта метод
Мифы.3и4 , Авито1.3

1. Определение размера выборки(срока) из мощности и MDE:
Тинькофф.2и6, Карпов - размер выборки, Мифы.7

2. Сплит-система
Тинькофф.2

3. Репрезентативность выборки, стратификация
Тинькофф.4, Авито2.3

4. Проверка метода с помощью FPR в A/A, или по мощности+FPR в A/A/B на искуственных данных:
Авито1.2, ВК1.2и1.4и1.5

5. Методы расчета А/B тестов, методы повышения мощности
Мифы.5и6, Авито1.4, Авито2.2и3и4

6. Сравнение методов
ВК.2и3и4, Авито2.5

7. Проблема подглядывания и методы досрочного прекращения теста
Карпов подглядывания, Учи.ру.1и2и3

8. Расчет срока теста по старым или предэксп. данным
Учи.ру.4, Авито2.1b

9. Выводы из результатов теста
Мифы9, Авито1.1и4
