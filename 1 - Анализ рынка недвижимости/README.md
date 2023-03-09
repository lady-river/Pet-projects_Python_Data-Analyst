<div class="application-main " data-commit-hovercards-enabled="" data-discussion-hovercards-enabled="" data-issue-and-pr-hovercards-enabled="">
<div class="">
<div class="clearfix container-xl px-3 px-md-4 px-lg-5 mt-4">
<div id="readme" class="Box md js-code-block-container js-code-nav-container js-tagsearch-file Box--responsive" data-tagsearch-path="Исследование_объявлений_о_продаже_квартир/README.md" data-tagsearch-lang="Markdown">
<div class="Box-body px-5 pb-5" data-target="readme-toc.content">
<article class="markdown-body entry-content container-lg">
<h2><strong>Описание проекта</strong></h2>
<div class="paragraph">В вашем распоряжении данные сервиса Яндекс Недвижимость &mdash; архив объявлений за несколько лет о продаже квартир в Санкт-Петербурге и соседних населённых пунктах.</div>
<div class="paragraph">Ваша задача &mdash; выполнить предобработку данных и изучить их, чтобы найти интересные особенности и зависимости, которые существуют на рынке недвижимости.</div>
<div class="paragraph">О каждой квартире в базе содержится два типа данных: добавленные пользователем и картографические. Например, к первому типу относятся площадь квартиры, её этаж и количество балконов, ко второму &mdash; расстояния до центра города, аэропорта и ближайшего парка.</div>
<h3>Инструкция по выполнению проекта</h3>
<div class="paragraph"><strong>Шаг 1.</strong> <strong>Откройте файл с данными и изучите общую информацию</strong></div>
<div class="paragraph">&nbsp;</div>
<ol start="1">
<li>Загрузите данные из файла в датафрейм.</li>
<li>Изучите общую информацию о полученном датафрейме.</li>
<li>Постройте общую гистограмму для всех числовых столбцов таблицы. Например, для датафрейма <code class="code-inline code-inline_theme_light">data</code> это можно сделать командой <code class="code-inline code-inline_theme_light">data.hist(figsize=(15, 20))</code>.</li>
</ol>
<div class="paragraph"><strong>Шаг 2. Предобработка данных</strong></div>
<ol start="1">
<li>Найдите и изучите пропущенные значения в столбцах:
<ul>
<li>Определите, в каких столбцах есть пропуски.</li>
<li>Заполните пропущенные значения там, где это возможно. Например, если продавец не указал число балконов, то, скорее всего, в его квартире их нет. Такие пропуски правильно заменить на 0. Если логичную замену предложить невозможно, то оставьте эти значения пустыми. Пропуски &mdash; тоже важный сигнал, который нужно учитывать.</li>
<li>В ячейке с типом <code class="code-inline code-inline_theme_light">markdown</code> укажите причины, которые могли привести к пропускам в данных.</li>
</ul>
</li>
<li>Рассмотрите типы данных в каждом столбце:
<ul>
<li>Найдите столбцы, в которых нужно изменить тип данных.</li>
<li>Преобразуйте тип данных в выбранных столбцах.</li>
<li>В ячейке с типом <code class="code-inline code-inline_theme_light">markdown</code> поясните, почему нужно изменить тип данных.</li>
</ul>
</li>
<li>
<div class="paragraph">Изучите уникальные значения в столбце с названиями и устраните неявные дубликаты. Например, &laquo;поселок Рябово&raquo; и &laquo;поселок городского типа Рябово&raquo;, &laquo;поселок Тельмана&raquo; и &laquo;посёлок Тельмана&raquo; &mdash; это обозначения одних и тех же населённых пунктов. Вы можете заменить названия в существующем столбце или создать новый с названиями без дубликатов.</div>
</li>
<li>
<div class="paragraph">Найдите и устраните редкие и выбивающиеся значения. Например, в столбце <code class="code-inline code-inline_theme_light">ceiling_height</code> может быть указана высота потолков <code class="code-inline code-inline_theme_light">25 м</code> и <code class="code-inline code-inline_theme_light">32 м</code>. Логично предположить, что на самом деле это вещественные значения: <code class="code-inline code-inline_theme_light">2.5 м</code> и <code class="code-inline code-inline_theme_light">3.2 м</code>. Попробуйте обработать аномалии в этом и других столбцах.
<ul>
<li>Если природа аномалии понятна и данные действительно искажены, то восстановите корректное значение.</li>
<li>В противном случае удалите редкие и выбивающиеся значения.</li>
<li>В ячейке с типом <code class="code-inline code-inline_theme_light">markdown</code> опишите, какие особенности в данных вы обнаружили.</li>
</ul>
</div>
</li>
</ol>
<div class="paragraph"><strong>Шаг 3. Добавьте в таблицу новые столбцы со следующими параметрами:</strong></div>
<ul>
<li>цена одного квадратного метра;</li>
<li>день недели публикации объявления (0 &mdash; понедельник, 1 &mdash; вторник и так далее);</li>
<li>месяц публикации объявления;</li>
<li>год публикации объявления;</li>
<li>тип этажа квартиры (значения &mdash; &laquo;&lrm;первый&raquo;, &laquo;последний&raquo;, &laquo;другой&raquo;);</li>
<li>расстояние до центра города в километрах (переведите из <em>м</em> в <em>км</em> и округлите до целых значений).</li>
</ul>
<div class="paragraph"><strong>Шаг 4. Проведите исследовательский анализ данных:</strong></div>
<ol start="1">
<li>Изучите следующие параметры объектов:
<ul>
<li>общая площадь;</li>
<li>жилая площадь;</li>
<li>площадь кухни;</li>
<li>цена объекта;</li>
<li>количество комнат;</li>
<li>высота потолков;</li>
<li>этаж квартиры;</li>
<li>тип этажа квартиры (&laquo;первый&raquo;, &laquo;последний&raquo;, &laquo;другой&raquo;);</li>
<li>общее количество этажей в доме;</li>
<li>расстояние до центра города в метрах;</li>
<li>расстояние до ближайшего аэропорта;</li>
<li>расстояние до ближайшего парка;</li>
<li>
<div class="paragraph">день и месяц публикации объявления.</div>
<div class="paragraph">Постройте отдельные гистограммы для каждого из этих параметров. Опишите все ваши наблюдения по параметрам в ячейке с типом <code class="code-inline code-inline_theme_light">markdown</code>.</div>
</li>
</ul>
</li>
<li>
<div class="paragraph">Изучите, как быстро продавались квартиры (столбец <code class="code-inline code-inline_theme_light">days_exposition</code>). Этот параметр показывает, сколько дней было размещено каждое объявление.
<ul>
<li>Постройте гистограмму.</li>
<li>Посчитайте среднее и медиану.</li>
<li>В ячейке типа <code class="code-inline code-inline_theme_light">markdown</code> опишите, сколько времени обычно занимает продажа. Какие продажи можно считать быстрыми, а какие &mdash; необычно долгими?</li>
</ul>
</div>
</li>
<li>
<div class="paragraph">Какие факторы больше всего влияют на общую (полную) стоимость объекта?</div>
<div class="paragraph">Изучите, зависит ли цена от:</div>
<ul>
<li>общей площади;</li>
<li>жилой площади;</li>
<li>площади кухни;</li>
<li>количества комнат;</li>
<li>этажа, на котором расположена квартира (первый, последний, другой);</li>
<li>
<div class="paragraph">даты размещения (день недели, месяц, год).</div>
<div class="paragraph">Постройте графики, которые покажут зависимость цены от указанных выше параметров. Для подготовки данных перед визуализацией вы можете использовать сводные таблицы.</div>
</li>
</ul>
</li>
<li>
<div class="paragraph">Посчитайте среднюю цену одного квадратного метра в 10 населённых пунктах с наибольшим числом объявлений. Выделите населённые пункты с самой высокой и низкой стоимостью квадратного метра. Эти данные можно найти по имени в столбце <code class="code-inline code-inline_theme_light">locality_name</code>.</div>
</li>
<li>
<div class="paragraph">Ранее вы посчитали расстояние до центра в километрах. Теперь выделите квартиры в Санкт-Петербурге с помощью столбца <code class="code-inline code-inline_theme_light">locality_name</code> и вычислите среднюю цену каждого километра. Опишите, как стоимость объектов зависит от расстояния до центра города.</div>
</li>
</ol>
<div class="paragraph"><strong>Шаг 5. Напишите общий вывод</strong></div>
<div class="paragraph">Опишите полученные результаты и зафиксируйте основной вывод проведённого исследования.</div>
<h3><strong>Оформление</strong></h3>
<div class="paragraph">Выполните задание в Jupyter Notebook. Заполните программный код в ячейках типа <code class="code-inline code-inline_theme_light">code</code>, текстовые пояснения &mdash; в ячейках типа <code class="code-inline code-inline_theme_light">markdown</code>. Примените форматирование и заголовки.</div>
<h3>Описание данных</h3>
<ul>
<li><code class="code-inline code-inline_theme_light">airports_nearest</code> &mdash; расстояние до ближайшего аэропорта в метрах (м)</li>
<li><code class="code-inline code-inline_theme_light">balcony</code> &mdash; число балконов</li>
<li><code class="code-inline code-inline_theme_light">ceiling_height</code> &mdash; высота потолков (м)</li>
<li><code class="code-inline code-inline_theme_light">cityCenters_nearest</code> &mdash; расстояние до центра города (м)</li>
<li><code class="code-inline code-inline_theme_light">days_exposition</code> &mdash; сколько дней было размещено объявление (от публикации до снятия)</li>
<li><code class="code-inline code-inline_theme_light">first_day_exposition</code> &mdash; дата публикации</li>
<li><code class="code-inline code-inline_theme_light">floor</code> &mdash; этаж</li>
<li><code class="code-inline code-inline_theme_light">floors_total</code> &mdash; всего этажей в доме</li>
<li><code class="code-inline code-inline_theme_light">is_apartment</code> &mdash; апартаменты (булев тип)</li>
<li><code class="code-inline code-inline_theme_light">kitchen_area</code> &mdash; площадь кухни в квадратных метрах (м&sup2;)</li>
<li><code class="code-inline code-inline_theme_light">last_price</code> &mdash; цена на момент снятия с публикации</li>
<li><code class="code-inline code-inline_theme_light">living_area</code> &mdash; жилая площадь в квадратных метрах (м&sup2;)</li>
<li><code class="code-inline code-inline_theme_light">locality_name</code> &mdash; название населённого пункта</li>
<li><code class="code-inline code-inline_theme_light">open_plan</code> &mdash; свободная планировка (булев тип)</li>
<li><code class="code-inline code-inline_theme_light">parks_around3000</code> &mdash; число парков в радиусе 3 км</li>
<li><code class="code-inline code-inline_theme_light">parks_nearest</code> &mdash; расстояние до ближайшего парка (м)</li>
<li><code class="code-inline code-inline_theme_light">ponds_around3000</code> &mdash; число водоёмов в радиусе 3 км</li>
<li><code class="code-inline code-inline_theme_light">ponds_nearest</code> &mdash; расстояние до ближайшего водоёма (м)</li>
<li><code class="code-inline code-inline_theme_light">rooms</code> &mdash; число комнат</li>
<li><code class="code-inline code-inline_theme_light">studio</code> &mdash; квартира-студия (булев тип)</li>
<li><code class="code-inline code-inline_theme_light">total_area</code> &mdash; общая площадь квартиры в квадратных метрах (м&sup2;)</li>
<li><code class="code-inline code-inline_theme_light">total_images</code> &mdash; число фотографий квартиры в объявлении</li>
</ul>
</article>
</div>
</div>
</div>
</div>
</div>
