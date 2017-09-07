---
title: Додавання напрямків руху по смугах
---

## Що таке напрямки руху по смугах

Напрямки руху по смугах це розмітка яка показує дозволені на перехресті напрямки руху по смугах.

Напрямки руху по смугах призначені для:
 * Інформування транспортних засобів які рухаються прямо та
  
 * Інформування транспортних засобів що змінюють напрямок руху

## Варіанти позначення напрямків руху по смугах

Існує загалом 12 різних варіантів позначення напрямків руху на дорогах

Опис та тег OSM | Умовний знак
--- | ---
Рух лише ліворуч<br>`turn:lanes = left` | ![left](https://cloud.githubusercontent.com/assets/8401827/13217928/1d2fc24e-d98c-11e5-9d20-c526fe6e7f01.jpg)
Рух лише праворуч<br>`turn:lanes = right` | ![right](https://cloud.githubusercontent.com/assets/8401827/13217945/424f36e0-d98c-11e5-99e7-9d178f2529a1.jpg)
Рух лише прямо<br>`turn:lanes = through` | ![through](https://cloud.githubusercontent.com/assets/8401827/13214156/f885d4b4-d973-11e5-9fb7-e9ecb70a932b.jpg)
Рух лише лівоворуч та прямо<br>`turn:lanes = left;through` | ![through left](https://cloud.githubusercontent.com/assets/8401827/13217986/80786072-d98c-11e5-99c6-db8665977550.png)
Рух лише ліворуч та прямо<br>`turn:lanes = right;through` | ![through_right](https://cloud.githubusercontent.com/assets/8401827/13218022/b8aa9352-d98c-11e5-87c2-d8c17ee68305.jpg)
Рух лише ліворуч, прямо та праворуч<br>`turn:lanes = left;through;right` | ![leftthroughright](https://cloud.githubusercontent.com/assets/8401827/13218061/027e10ee-d98d-11e5-9747-c6867e0787b0.JPG)
Рух лише ліворуч та праворуч<br>`turn:lanes = left;right` | ![left_right](https://cloud.githubusercontent.com/assets/8401827/13217579/8f833c66-d989-11e5-9b2c-dc98fdff09b2.png)
Плавний рух лише ліворуч<br>`turn:lanes = slight_left` | ![slightleft](https://cloud.githubusercontent.com/assets/8401827/13218207/e450feaa-d98d-11e5-938c-a3956de2f7ba.png)
Плавний рух лише праворуч<br>`turn:lanes = slight_right` | ![slightright](https://cloud.githubusercontent.com/assets/8401827/13218219/07052b56-d98e-11e5-8fc0-82b945fb95c6.png)
Кінець смуги та перехід у смугу ліворуч<br>`turn:lanes = merge_to_left` | ![merge to left](https://cloud.githubusercontent.com/assets/8401827/13218244/2ca1fd6c-d98e-11e5-8be9-cb64271f5991.png)
Кінець смуги та перехід у смугу праворуч<br>`turn:lanes = merge_to_right` | ![fahrbahn_2](https://cloud.githubusercontent.com/assets/8401827/13218183/bc5d0790-d98d-11e5-9781-307f80cc0732.png)
Смуга лише для повороту ліворуч<br>`turn:lanes:both_ways = *` | ![turn lanes both ways](https://cloud.githubusercontent.com/assets/8401827/13217721/a2594d48-d98a-11e5-87f1-11e11ebf57ec.png)

  ![](http://pdd.ua/r/r/EEB7A996-D8DC-40FC-87EA-01F3E115BC7C/m_1.18_4.jpg)
  _Позначення напрямків руху на проїзній частині_ - © [pdd.ua](http://pdd.ua/ua/34/1.18/)

## Підготовка до картографування напрямків руху по смугах у JOSM

Перед початком картографування напрямків руху по смугах потрібно зробити наступні налаштування у JOSM. 

### 1. Налаштування відображення карти. 

Оберіть **`Preferences > Map Settings`**

  1.1. Додайте стиль для відображення смуг руху.
  
  **`Map Paint Styles > Lane and road attributes`**

  ![lane_and_road_attributes](https://cloud.githubusercontent.com/assets/13744156/13218788/c55fab96-d991-11e5-89b2-b281986d704e.gif)

  1.2. Додайте набір тегів для смуг руху.
  
  **`Tagging Presets > Lane attributes`**

  ![tagging_presets](https://cloud.githubusercontent.com/assets/13744156/13218902/ad15c902-d992-11e5-872b-1bde24f27f5b.gif)

  1.3. Filter out non-road features with inverse filter: `boundary: | leisure: | landuse: | waterway: | amenity: | natural: | building:`

### 2. Встановлення плагінів

  2.1. Knife-tool. 
  
  Входить до складу плагіну auto-tools. [Інструкція з встановлення](https://gist.github.com/jothirnadh/a10daeaef1498537ea56f0a65f7fdbc2)
  
  2.2. turnlanes-tagging.
  
  Оберіть **`Preferences > Plugins > turnlanes-tagging`**

## Картографування напрямків руху по смугах

* Визначте на знімку перехрестя з позначеними напрямками руху по смугах.

  ![roads_markings](https://cloud.githubusercontent.com/assets/126868/11710074/b58b52e4-9f42-11e5-971a-000a699a0b6d.png)

* Поділіть лінію дороги на сегменти виходячи с загальної кількості смуг на сегменті. Найпростішім шляхом для цього є використання [Knife_tool](https://gist.github.com/jothirnadh/a10daeaef1498537ea56f0a65f7fdbc2)

  ![residential_road](https://cloud.githubusercontent.com/assets/369696/13223732/34cf7ffa-d98e-11e5-9a33-8f40f6498004.png)

* Для кожного сегменту вкажіть тег `turn:lanes` спираючись на дорожню розмітку з урахуванням напрямку лінії дороги. Наприклад. `turn:lanes=left|left;through|through`. Більше прикладів можна знайти тут [OSM turn:lanes](http://wiki.openstreetmap.org/wiki/RU:Key:turn:lanes).
  ![oneway_turn:lanes_tagging](https://cloud.githubusercontent.com/assets/8401827/13252110/a6bdea8a-da5a-11e5-8c79-aa15c0c15f68.gif)

* Для сегментів доріг, рух на яких здійснюється в обох напрямках, необхідно вказати `turn:lanes:forward=` (кількість смуг в напрямку що співпадає з напрямком лінії дороги) та `turn:lanes:backward=` (кількість смуг в напрямку протилежному напрямку  лінії дороги).

  ![bidirectional_tagging](https://cloud.githubusercontent.com/assets/13744156/13219545/acd78f62-d996-11e5-85eb-3e05a7b79d3b.gif)

* Перевірте правильність заповнення тегів використовуючи стиль `Lane attributes`.

  ![lane_attributes](https://cloud.githubusercontent.com/assets/8401827/13251884/ddcbdd54-da58-11e5-86ae-c4a2918c9577.gif)

* Найпростіший шлях для цього викоростання плагіну **[turnlanes-tagging](https://www.mapbox.com/blog/turnlanes-tagging/)**

![turnlenes](https://cloud.githubusercontent.com/assets/8401827/17246767/d086ef48-55ab-11e6-8bce-46c434cb9005.gif)

## Напрямки руху по смугах та відношення

[Відношення](http://wiki.openstreetmap.org/wiki/Uk:Relation) використовуються з різною метою – для позначення [заборони руху в певних напрямках](http://wiki.openstreetmap.org/wiki/RU:Отношения_-_ограничения) або обʼєднання окремих шляхів в один [маршрут](http://wiki.openstreetmap.org/wiki/Uk:Relation:route).
JOSM допомагає нам впоратися з ними. Але іноді ми стикаємося з неправильно позначеними відношеннями. JOSM повідомить про це під час завантаження змін. Ви можете [ігнорувати повідомлення рівня "Попередження"](https://github.com/mapbox/mapping/issues/153#issuecomment-185679507) (якщо ви тільки розділили дорогу та не редагували відношення вручну) але вам потрібно виправити всі помилки "Errors".

## Контроль якості картографування напрямків руху по смугах.

Багато окремих випадків картографування напрямків руху по смугах наведено у [#153](https://github.com/mapbox/mapping/issues/153) та [#144](https://github.com/mapbox/mapping/issues/144). Всі ці сценарії наведені в одному місці з метою перевірки.

## Окремі випадки що трапляються під час картографування 

### 1. Паркувальні смуги

У сполучених Штатах паркувальні місця позначаються одним з [трьох способів](http://mutcd.fhwa.dot.gov/htm/2009/part3/fig3b_21_longdesc.htm):

  ![parking_lanes](https://cloud.githubusercontent.com/assets/8401827/13172245/326a7bb6-d71d-11e5-8617-a2516f75144b.png)

Приклад позначення паркувальних місць

  [![boxes](https://upload.wikimedia.org/wikipedia/commons/thumb/0/03/J.S._Shingler_Bldg_%28East_face%29%2C_McLendon_St%2C_Ashburn.JPG/320px-J.S._Shingler_Bldg_%28East_face%29%2C_McLendon_St%2C_Ashburn.JPG)](https://commons.wikimedia.org/wiki/File:J.S._Shingler_Bldg_%28East_face%29,_McLendon_St,_Ashburn.JPG)

### 2. Підрахунок кількості смуг.Counting number of turn lanes

У випадку якщо на дорозі відсутня чітка розмітка паркувальних місць та є припарковані автомобілі, смуги на яких вони припарковані враховуються в загальну кількість.
Див. приклад на малюнку нижче:

 ![number_of_lanes](https://cloud.githubusercontent.com/assets/8401827/13142482/5b26d0a0-d663-11e5-90cd-4a65d75e7248.png)

### 3. Визначення початку відрізку лінії дороги на якому позначаються напрямки руху за смугами.

Поділ лінії дороги потрібно здійснювати у точці де фактично починається розмітка (як наведено на малюнку нижче) і ні в якому разі не раніше.

  ![turn:lanes_start](https://cloud.githubusercontent.com/assets/8401827/13110125/0fe83ad0-d5a4-11e5-82ff-00245d0ba043.png)

### 4. Визначення закінчення відрізку лінії дороги на якому позначаються напрямки руху за смугами.

Відрізок лінії дороги на якому позначаються напрямки руху по смугах повинен закінчуватися на першому перехресті від його початку

  ![turn:lanes_end](https://cloud.githubusercontent.com/assets/8401827/13143057/4ff2b3c6-d667-11e5-8069-b028fabf7587.png)

### 5. Смуги в напрямку що співпадає з намрямком лінії дороги.

У випадку дороги рух на якій здійснюється в обох напрямках, ключ [turn:lanes:forward=*](http://wiki.openstreetmap.org/wiki/Uk:Forward_%26_backward,_left_%26_right) описує лише смуги у напрямку що співпадає з напрямком лінії дороги. Після додавання напрямків руху ви повинні побачини позначки у напрямку лінії дороги (**напрямок що вказується стрілкою на кінці лінії дороги**).

  ![turn:lanes:forward](https://cloud.githubusercontent.com/assets/8401827/13175904/c5c922fc-d733-11e5-91b1-c0f9e5181fda.gif)

### 6. Смуги в напрямку протилежному намрямку лінії дороги.

У випадку дороги рух на якій здійснюється в обох напрямках, ключ [turn:lanes:backward=*](http://wiki.openstreetmap.org/wiki/Uk:Forward_%26_backward,_left_%26_right) описує лише смуги у напрямку протилежному напрямку лінії дороги. Після додавання напрямків руху ви повинні побачини позначки у напрямку протилежному напрямку лінії дороги (**напрямок протилежний стрілці на кінці лінії дороги**).

  ![turn:lanes:backward](https://cloud.githubusercontent.com/assets/13744156/13172709/859957c4-d71f-11e5-8cd9-ea154ad5d2e8.gif)

### 7. Дороги з розділювальною смугою.

У вападку коли ви бачити дорогу позначену я суцільна проїжджа части (одна лінія), але на знімку чітко видно розділювальну смугу потрібно поділити лінію дороги на дві окремі лінії (проїжджі частини). Після поділу необхідно додати до кожної лінії тег `turn:lanes` та вказати кількість смуг.

Ділити на окремі проїжджі частини потрібно коли:
 - ви читко бачити розділювальну смугу між проїжджими частинами;
 - **дорога не має відношень (relation)**.

![dualcarriageway](https://cloud.githubusercontent.com/assets/8401827/13393542/117b59aa-df08-11e5-8fd3-21a931531f84.png)

### 8. Велосипедні доріжки та узбічча

Велосипедні доріжки та узбічча не враховуються в числі смуг. 

* Обидві дороги мають по дві смуги `lanes=2`

  ![bicycle+shoulders](https://cloud.githubusercontent.com/assets/126868/11715007/628dd90a-9f64-11e5-9e22-58614d2afbf6.png)

* Дорога має три смуги `lanes=3`. Дві велосипедні доріжки не враховуються.

  ![bicycle_lanes](https://cloud.githubusercontent.com/assets/13744156/13172922/adc69f08-d720-11e5-8600-7a606d2e9bae.png)

* Не враховуються також велосипедні доріжки які проходять всередині дороги

  ![xyz2](https://cloud.githubusercontent.com/assets/8401827/13495220/79a65aca-e16f-11e5-83e7-24d3e4f53ad0.png)

* Можна використовувати додатковий шар `Strava global-heat cycle` для первірки того чи є смуга велосипедною доріжкою.
`tms[16]:http://globalheat.strava.com/tiles/cycling/color3/{zoom}/{x}/{y}.png`

### 9. Смуги зображені як окрема дорога

Напрямок руху не потрібно вказувати якщо смуга зображена як окрема дорога

  ![lane_as_separate_way](https://cloud.githubusercontent.com/assets/13744156/13173428/6694c468-d723-11e5-96be-b95502b9f58a.png)

### 10. Двонаправлені смуги

На знімку зображена смуга з умовним знаком що дозволяю рух в обох напрямках одночасно.

Для позначення таких смуг використовується тег `turn:lanes:both_ways=*`

  ![turn:lanes:both_ways](https://cloud.githubusercontent.com/assets/8401827/12642951/0162ff9c-c5df-11e5-8a14-a41f263ae086.png)

Жовті лінії з обох боків смуги також вказують на двонаправлену смугу `turn:lanes:both_ways=*`

![screen shot 2016-05-16 at 4 12 49 pm](https://cloud.githubusercontent.com/assets/1933377/15287587/8dd24396-1b81-11e6-8527-b84814804175.png)

![screen shot 2016-05-16 at 4 13 00 pm](https://cloud.githubusercontent.com/assets/1933377/15287591/9165c50a-1b81-11e6-9521-93cea4b7be16.png)

### 11. Плагін Mapillary для перевірки напрямків руху за смугами

Ксмічні знімки в деяких місцях не дуже чітки а місцями смуги закриті автомобілями. В цих випадках можна використовувати `Mapillary plugin`. Якщо в даному місці є знімок Mapillary його можна використовувати для визначення напрямків руху за смугами спираючись на дорожні знаки на цьому знімку.

  ![turnlanes_mapillary](https://cloud.githubusercontent.com/assets/4470913/12884912/6b405d1e-ce87-11e5-8d0f-cd8a8a8b3dfd.gif)

### 12. Острівці безпеки

Це місця на проїжджій частині на які заборонений вʼїзд автотраспорту.

У всіх випадках наведених нижче острівці безпеки не враховуються в число смуг.

![screen shot 2016-03-15 at 3 36 36 pm](https://cloud.githubusercontent.com/assets/8401827/13776503/84c34002-ead0-11e5-911d-0581fe9173b7.png)

![screen shot 2016-03-14 at 4 46 03 pm](https://cloud.githubusercontent.com/assets/8401827/13776504/84e64138-ead0-11e5-81f0-7918311ec6dc.png)

![screen shot 2016-03-14 at 4 46 29 pm](https://cloud.githubusercontent.com/assets/8401827/13776505/84e71888-ead0-11e5-9135-553c11d99d12.png)

### 13. Смуги для розвороту

Смуги призначені виключно для розвороту позначаються спеціальним тегом. У випадку наведеному на малюнку це виглядає наступним чином `turn:lane:reverse|||`. 

![screen shot 2016-03-14 at 2 25 28 pm](https://cloud.githubusercontent.com/assets/8401827/13776502/84944b6c-ead0-11e5-92fa-0bb2951760ef.png)

### 14. The order of the directions and valid combinations of values

  #### Використання `none` 
  
  `none` є дозволеним значенния але **не** у поєднанні з іншими
  
  ✅ `turn:lanes=none|right` еквівалентно `turn:lanes=|right` - ми використовуємо `none` для "_кращої читабельності_"

  👎  `turn:lanes=left||none|merge_to_right` - ця комбінація значень дозволена, але змішування `none` та `||` (пусто) не є гарним прикладом 

  👍  Використовуйте `turn:lanes=left|none|none|merge_to_right` або `turn:lanes=left|||merge_to_right`  
  
  ❎ `turn:lanes=none|none|none` or `turn:lanes=||` - В цьому випадку тег `turn:lanes` є надлишковим. Потрібно лише вказати загальну кількість смуг `lanes=3` 

  ❎ `turn:lanes=none|none;slight_right` - це не дозволена комбінація - "_втрачене позначення повороту_"  на крайній правій смузі. Замість цього потрібно використовувати (базуючись на https://github.com/mapbox/mapping/issues/180#issuecomment-225574666)

```
lanes=2
turn:lanes=none|through;slight_right
transit:lanes=continue|new_on_right
```  

#### Використання значень `*right` та `*left`

  ✅ `turn:lanes=left|none|none` або `turn:lanes=||right` або `turn:lanes=merge_to_right||` або `turn:lanes=left|left;through|none|slight_right|right|right`- 👍  

  ❎  `turn:lanes=|right|left|` або `turn:lanes=none|right|left|through` або `turn:lanes=none|left|none`- 👎  смуги що ідуть в одному напрямку не можуть перетинатися одна з одною

#### Використання значення `reverse`
 
Значення `reverse` (розворот) може використовуватися лише для крайньої лівої смуги у випадку правосторонього руху або для крайньої лівої смуги у випадку лівосторонього руху.

### 15.

_to be continued …_

### Матеріали для подальшого вивчення 
* [Mapping turn lanes: OSM wiki](http://wiki.openstreetmap.org/wiki/RU:Key:turn)
* [Mapping turn lanes in OpenStreetMap by Andrey Golovin](https://www.mapbox.com/blog/turn-lanes-mapping/)
* Diary post by @Andygol : [Mapping turn lanes in OpenStreetMap](http://www.openstreetmap.org/user/andygol/diary/35489#)
