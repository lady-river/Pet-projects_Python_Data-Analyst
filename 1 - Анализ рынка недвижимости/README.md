<div class="application-main " data-commit-hovercards-enabled="" data-discussion-hovercards-enabled="" data-issue-and-pr-hovercards-enabled="">
<div class="">
<div class="clearfix container-xl px-3 px-md-4 px-lg-5 mt-4">
<div>
<div id="readme" class="Box md js-code-block-container js-code-nav-container js-tagsearch-file Box--responsive" data-tagsearch-path="Исследование_объявлений_о_продаже_квартир/README.md" data-tagsearch-lang="Markdown">
<div class="Box-body px-5 pb-5" data-target="readme-toc.content">
<article class="markdown-body entry-content container-lg">
<h1 dir="auto" tabindex="-1">Исследование объявлений о продаже квартир</h1>
<h2 dir="auto" tabindex="-1"><a id="user-content-описание-проекта" class="anchor" href="https://github.com/raspopovaa/Pet-Project-Data-Analyst/tree/main/%D0%98%D1%81%D1%81%D0%BB%D0%B5%D0%B4%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5_%D0%BE%D0%B1%D1%8A%D1%8F%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9_%D0%BE_%D0%BF%D1%80%D0%BE%D0%B4%D0%B0%D0%B6%D0%B5_%D0%BA%D0%B2%D0%B0%D1%80%D1%82%D0%B8%D1%80#%D0%BE%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%BE%D0%B5%D0%BA%D1%82%D0%B0" aria-hidden="true"></a>Описание проекта</h2>
<p dir="auto">В вашем распоряжении данные сервиса о недвижимости &mdash; архив объявлений о продаже квартир в Санкт-Петербурге и соседних населённых пунктах за несколько лет. Нужно научиться определять рыночную стоимость объектов недвижимости. Ваша задача &mdash; установить параметры. Это позволит построить автоматизированную систему: она отследит аномалии и мошенническую деятельность.</p>
<p dir="auto">По каждой квартире на продажу доступны два вида данных. Первые вписаны пользователем, вторые &mdash; получены автоматически на основе картографических данных. Например, расстояние до центра, аэропорта, ближайшего парка и водоёма. Инструкция по выполнению проекта</p>
<h2 dir="auto" tabindex="-1"><a id="user-content-шаг-1-откройте-файл-с-данными-и-изучите-общую-информацию" class="anchor" href="https://github.com/raspopovaa/Pet-Project-Data-Analyst/tree/main/%D0%98%D1%81%D1%81%D0%BB%D0%B5%D0%B4%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5_%D0%BE%D0%B1%D1%8A%D1%8F%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9_%D0%BE_%D0%BF%D1%80%D0%BE%D0%B4%D0%B0%D0%B6%D0%B5_%D0%BA%D0%B2%D0%B0%D1%80%D1%82%D0%B8%D1%80#%D1%88%D0%B0%D0%B3-1-%D0%BE%D1%82%D0%BA%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D1%84%D0%B0%D0%B9%D0%BB-%D1%81-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8-%D0%B8-%D0%B8%D0%B7%D1%83%D1%87%D0%B8%D1%82%D0%B5-%D0%BE%D0%B1%D1%89%D1%83%D1%8E-%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8E" aria-hidden="true"></a>Шаг 1. Откройте файл с данными и изучите общую информацию</h2>
<h2 dir="auto" tabindex="-1"><a id="user-content-шаг-2-предобработка-данных" class="anchor" href="https://github.com/raspopovaa/Pet-Project-Data-Analyst/tree/main/%D0%98%D1%81%D1%81%D0%BB%D0%B5%D0%B4%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5_%D0%BE%D0%B1%D1%8A%D1%8F%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9_%D0%BE_%D0%BF%D1%80%D0%BE%D0%B4%D0%B0%D0%B6%D0%B5_%D0%BA%D0%B2%D0%B0%D1%80%D1%82%D0%B8%D1%80#%D1%88%D0%B0%D0%B3-2-%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85" aria-hidden="true"></a>Шаг 2. Предобработка данных</h2>
<p dir="auto">Определите и изучите пропущенные значения: Для некоторых пропущенных значений можно предположить логичную замену. Например, если человек не указал число балконов &mdash; скорее всего, их нет. Такие пропуски правильно заменить на 0. Для других типов данных нет подходящего значения на замену. В этом случае правильно оставить эти значения пустыми. Отсутствие значения &mdash; тоже важный сигнал, который не нужно прятать. Заполните пропуски, где это уместно. Опишите, почему вы решили заполнить пропуски именно в этих столбцах и как выбрали значения. Укажите причины, которые могли привести к пропускам в данных. Приведите данные к нужным типам: Поясните, в каких столбцах нужно изменить тип данных и почему.</p>
<h2 dir="auto" tabindex="-1"><a id="user-content-шаг-3-посчитайте-и-добавьте-в-таблицу" class="anchor" href="https://github.com/raspopovaa/Pet-Project-Data-Analyst/tree/main/%D0%98%D1%81%D1%81%D0%BB%D0%B5%D0%B4%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5_%D0%BE%D0%B1%D1%8A%D1%8F%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9_%D0%BE_%D0%BF%D1%80%D0%BE%D0%B4%D0%B0%D0%B6%D0%B5_%D0%BA%D0%B2%D0%B0%D1%80%D1%82%D0%B8%D1%80#%D1%88%D0%B0%D0%B3-3-%D0%BF%D0%BE%D1%81%D1%87%D0%B8%D1%82%D0%B0%D0%B9%D1%82%D0%B5-%D0%B8-%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D1%8C%D1%82%D0%B5-%D0%B2-%D1%82%D0%B0%D0%B1%D0%BB%D0%B8%D1%86%D1%83" aria-hidden="true"></a>Шаг 3. Посчитайте и добавьте в таблицу</h2>
<ul dir="auto">
<li>цену квадратного метра;</li>
<li>день недели, месяц и год публикации объявления;</li>
<li>этаж квартиры; варианты &mdash; первый, последний, другой;</li>
<li>соотношение жилой и общей площади, а также отношение площади кухни к общей.</li>
</ul>
<h2 dir="auto" tabindex="-1"><a id="user-content-шаг-4-проведите-исследовательский-анализ-данных-и-выполните-инструкции" class="anchor" href="https://github.com/raspopovaa/Pet-Project-Data-Analyst/tree/main/%D0%98%D1%81%D1%81%D0%BB%D0%B5%D0%B4%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5_%D0%BE%D0%B1%D1%8A%D1%8F%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9_%D0%BE_%D0%BF%D1%80%D0%BE%D0%B4%D0%B0%D0%B6%D0%B5_%D0%BA%D0%B2%D0%B0%D1%80%D1%82%D0%B8%D1%80#%D1%88%D0%B0%D0%B3-4-%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D0%B4%D0%B8%D1%82%D0%B5-%D0%B8%D1%81%D1%81%D0%BB%D0%B5%D0%B4%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B8%D0%B9-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D0%B7-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8-%D0%B2%D1%8B%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5-%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8" aria-hidden="true"></a>Шаг 4. Проведите исследовательский анализ данных и выполните инструкции</h2>
<ul dir="auto">
<li>Изучите следующие параметры: площадь, цена, число комнат, высота потолков. Постройте гистограммы для каждого параметра.</li>
<li>Изучите время продажи квартиры. Постройте гистограмму. Посчитайте среднее и медиану. Опишите, сколько обычно занимает продажа. Когда можно считать, что продажи прошли очень быстро, а когда необычно долго?</li>
<li>Уберите редкие и выбивающиеся значения. Опишите, какие особенности обнаружили.</li>
<li>Какие факторы больше всего влияют на стоимость квартиры? Изучите, зависит ли цена от площади, числа комнат, удалённости от центра. Изучите зависимость цены от того, на каком этаже расположена квартира: первом, последнем или другом. Также изучите зависимость от даты размещения: дня недели, месяца и года.</li>
<li>Выберите 10 населённых пунктов с наибольшим числом объявлений. Посчитайте среднюю цену квадратного метра в этих населённых пунктах. Выделите населённые пункты с самой высокой и низкой стоимостью жилья. Эти данные можно найти по имени в столбце locality_name.</li>
<li>Изучите предложения квартир: для каждой квартиры есть информация о расстоянии до центра. Выделите квартиры в Санкт-Петербурге (locality_name). Ваша задача &mdash; выяснить, какая область входит в центр. Создайте столбец с расстоянием до центра в километрах: округлите до целых значений. После этого посчитайте среднюю цену для каждого километра. Постройте график: он должен показывать, как цена зависит от удалённости от центра. Определите границу, где график сильно меняется, &mdash; это и будет центральная зона.</li>
<li>Выделите сегмент квартир в центре. Проанализируйте эту территорию и изучите следующие параметры: площадь, цена, число комнат, высота потолков. Также выделите факторы, которые влияют на стоимость квартиры (число комнат, этаж, удалённость от центра, дата размещения объявления). Сделайте выводы. Отличаются ли они от общих выводов по всему городу?</li>
</ul>
<h2 dir="auto" tabindex="-1"><a id="user-content-шаг-5-напишите-общий-вывод" class="anchor" href="https://github.com/raspopovaa/Pet-Project-Data-Analyst/tree/main/%D0%98%D1%81%D1%81%D0%BB%D0%B5%D0%B4%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5_%D0%BE%D0%B1%D1%8A%D1%8F%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9_%D0%BE_%D0%BF%D1%80%D0%BE%D0%B4%D0%B0%D0%B6%D0%B5_%D0%BA%D0%B2%D0%B0%D1%80%D1%82%D0%B8%D1%80#%D1%88%D0%B0%D0%B3-5-%D0%BD%D0%B0%D0%BF%D0%B8%D1%88%D0%B8%D1%82%D0%B5-%D0%BE%D0%B1%D1%89%D0%B8%D0%B9-%D0%B2%D1%8B%D0%B2%D0%BE%D0%B4" aria-hidden="true"></a>Шаг 5. Напишите общий вывод</h2>
<h2 dir="auto" tabindex="-1"><a id="user-content-описание-данных" class="anchor" href="https://github.com/raspopovaa/Pet-Project-Data-Analyst/tree/main/%D0%98%D1%81%D1%81%D0%BB%D0%B5%D0%B4%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5_%D0%BE%D0%B1%D1%8A%D1%8F%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9_%D0%BE_%D0%BF%D1%80%D0%BE%D0%B4%D0%B0%D0%B6%D0%B5_%D0%BA%D0%B2%D0%B0%D1%80%D1%82%D0%B8%D1%80#%D0%BE%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85" aria-hidden="true"></a><strong>Описание данных</strong></h2>
<ul dir="auto">
<li><em>airports_nearest</em>&nbsp;&mdash; расстояние до ближайшего аэропорта в метрах (м)</li>
<li><em>balcon</em>&nbsp;&mdash; число балконов</li>
<li><em>ceiling_height</em>&nbsp;&mdash; высота потолков (м)</li>
<li><em>cityCenters_nearest</em>&nbsp;&mdash; расстояние до центра города (м)</li>
<li><em>days_exposition</em>&nbsp;&mdash; сколько дней было размещено объявление (от публикации до снятия)</li>
<li><em>first_day_exposition</em>&nbsp;&mdash; дата публикации</li>
<li><em>floor</em>&nbsp;&mdash; этаж</li>
<li><em>floors_total</em>&nbsp;&mdash; всего этажей в доме</li>
<li><em>is_apartment</em>&nbsp;&mdash; апартаменты (булев тип)</li>
<li><em>kitchen_area</em>&nbsp;&mdash; площадь кухни в квадратных метрах (м&sup2;)</li>
<li><em>last_price</em>&nbsp;&mdash; цена на момент снятия с публикации</li>
<li><em>living_area</em>&nbsp;&mdash; жилая площадь в квадратных метрах (м&sup2;)</li>
<li><em>locality_name</em>&nbsp;&mdash; название населённого пункта</li>
<li><em>open_plan</em>&nbsp;&mdash; свободная планировка (булев тип)</li>
<li><em>parks_around3000</em>&nbsp;&mdash; число парков в радиусе 3 км</li>
<li><em>parks_nearest</em>&nbsp;&mdash; расстояние до ближайшего парка (м)</li>
<li><em>ponds_around3000</em>&nbsp;&mdash; число водоёмов в радиусе 3 км</li>
<li><em>ponds_nearest</em>&nbsp;&mdash; расстояние до ближайшего водоёма (м)</li>
<li><em>rooms</em>&nbsp;&mdash; число комнат</li>
<li><em>studio</em>&nbsp;&mdash; квартира-студия (булев тип)</li>
<li><em>total_area</em>&nbsp;&mdash; площадь квартиры в квадратных метрах (м&sup2;)</li>
<li><em>total_images</em>&nbsp;&mdash; число фотографий квартиры в объявлении</li>
</ul>
</article>
</div>
</div>
<div><details class="details-reset details-overlay details-overlay-dark "><summary class="btn-invisible btn" role="button" data-view-component="true">Give feedback</summary></details></div>
</div>
</div>
</div>
</div>
<footer class="footer width-full container-xl p-responsive"></footer>
<p>&nbsp;</p>
