# EveOnline-PI
Гайд по планетарной промышленности Eve Online.

## 1. 🎯 Цели и задачи.
**Цель:** Предоставить базовые знания и базовые алгоритмы расчетов и производственных цепочек **планетарки**.

**Для кого:** игроки, которые хотят оптимизировать производственные цепочки без погружения в гипермикроменеджмент.

---

⚙️ **Базовые допущения**
1. **Читатель знаком с:**  
   - Интерфейсом добычи планетарных ресурсов.  
   - Механикой добычи (экстракторы, фабрики, хранилища)  
   - Основами логистики (POCO, шаттлы)  
2. **Фокус:** формулы, анализ рынка, баланс «прибыль/время»  
3. **Источники данных:** EVE Marketer или ESI API  

---

⚖️ **Принцип баланса**

Мы избегаем стратегий типа:

> «Построй 50 фабрик на 10 аккаунтах — профит 500M/час».

**Почему?**

- Высокие временные затраты на настройку и логистику;

- Риск «выгорания» от рутины.

**Наша задача:**

Определить «золотую середину» — 3 планетарщика на аккаунт с доходом 850-950M ISK/месяц с каждого при 15-20 минутах затрат времени на все.


## 2. Инфраструктура.

**Характеристики командных центров:**
| Уровень |	Емкость процессора | Энергия |
|---------|--------------------|---------|
|0|1,675 tf|6,000 MW|
|1|7,057 tf|9,000 MW|
|2|12,136 tf|12,000 MW|
|3|17,215 tf|15,000 MW|
|4|21,315 tf|17,000 MW|
|5|25,415 tf|19,000 MW|

Коммандный центр это энергетический центр всей планетарной инфраструктуры, уровнем его улучшения определяется какое колличество инфраструктуры мы установить на планету.

---

**Характеристики структур:**

|Название|Процессор|Энергия|Использование|
|-|-|-|-|
|Extractor Control Unit|400 tf|2600 MW|Добыча Р0|
|Extractor Head|110 tf|550 MW|В добыче|
|Basic Industry Facility|200 tf|800 MW|Производит Р1|
|Advanced Industry Facility|500 tf|700 MW|Производит Р2-Р3|
|High-Tech Industry Facility|1100 tf|400 MW|Производит Р4|
|Storage Facility|500 tf|700 MW|Хранит 12,000 m3|
|Launchpad|3600 tf|700 MW|Хранит 10,000 m3|

## 3. Первые расчеты


***
Наконец мы пришли к первым расчетам. Как мы видим планеты оказываются не резиновые, и количество инфраструктуры которое мы можем там разместить ограничено.

Исходя из имеющихся ограничений, давайте рассчитаем наиболее эффективный вариант использования планеты.

**За основу мы возьмем персонажа со следующими навыками:**
* Interplanetary Consolidation - 4
* Command Center Upgrades - 4

**Для начала рассмотрим первые варианты:**
* Добыча Р0
* Добыча Р0 -> производство P1

> Другие варианты мы не рассматриваем, поскольку для производства Р2 ресурса требуется 2 вида P0, а разместить 2 экстрактора в и несколько заводов просто невозможно.

Учитывая вышеприведенные данные мы знаем, что в нашем распоряжении CPU - 21,315 tf и энергия - 17,000 MW. В обоих вариантах нам потребуется Launchpad (3600 tf	) (700 MW) и Storage Facility (500 tf) (700 MW), так же за базу мы возьмем 2000 km соединений, а это (416 tf) (311 MW). Всего использовали 4516 tf и 1711 MW.

Таким образом свободный остаток ресурсов у нас следующий CPU 16799 Power 15289 MW

За тестовый ресурс мы возьмем самый дорогой на момент написания гайда Proteins - 821.50 ISK (P1) и Complex Organisms - 5.24 ISK (P0)

**Вариант 1**

Нам потребуется экстрактор и 10 добывающих головок (1500 tf) (8100 MW) свободный остаток ресурсов (15299 tf) (7189 MW). Как мы видим второй полноценный комплект экстрактора разместить мы уже не сможем посколько нам не хватит Power, да и в этом нет никакого смысла посколько это не удобно.

При суточном цикле добычи на достаточно богатой планете, мы будем добывать ~ 48 000 ресурса в час _(цифра получена опытным путем с учетом средних показателей за месяц)_

24 х 48,000 = 1,152,000 в сутки х 5.24 ISK = 6,036,480 х 30 = **181,094,400 ISK** за 30 дней. При условии что у нас 5 планет на одном персонаже мы имеем **905,472,000 ISK** в месяц грязными. Из этой суммы еще предстоит вычесть стоимость доставки, а также налоги и сборы при продаже.

**Вариант 2**

Как и в первом варианте нам понадобится экстрактор и 10 добывающих головок (1500 tf) (8100 MW) свободный остаток ресурсов также составит (15299 tf) (7189 MW).

Запаса по процессору у нас достаточно, по этому посчитаем только Power 7189 / 800 = 8,98625 из этого расчета мы видим, что у нас спокойно еще поместятся 8 Basic Industry Facility.

Забегая немного вперед посмотрим на характеристики заводов, набор характеристик для всех видов заводов одинаков, посмотрим на характеристики P1 завода, которые будут нами использоваться в расчетах: 
* **Время цикла** - 30 минут
* **Количество потребляемого ресурса** - 3000
* **Количество производимого ресурса** - 20
