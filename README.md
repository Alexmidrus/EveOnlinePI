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

Определить «золотую середину» — 3 планетарщика на аккаунт с доходом 850-950M ISK/месяц с каждого при 15-20 минутах управления.


## 2. Базовые цифры.

**Характеристики командных центров:**
| Уровень |	Емкость процессора | Энергия |
|---------|--------------------|---------|
|0|1,675 tf|6,000 MW|
|1|7,057 tf|9,000 MW|
|2|12,136 tf|12,000 MW|
|3|17,215 tf|15,000 MW|
|4|21,315 tf|17,000 MW|
|5|25,415 tf|19,000 MW|

Коммандный ценрт это энергетический центр всей планетарной инфраструктуры, уровнем его улучшения определяется какое колличество инфраструктуры мы установить на планету.

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

---



## 3. Анализ спроса, профитность, выбор ресурса для производство

## 4. Расчеты на примере


