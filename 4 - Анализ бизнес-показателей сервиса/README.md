<div class="application-main " data-commit-hovercards-enabled="" data-discussion-hovercards-enabled="" data-issue-and-pr-hovercards-enabled="">
<div class="">
<div class="clearfix container-xl px-3 px-md-4 px-lg-5 mt-4">
<div id="readme" class="Box md js-code-block-container js-code-nav-container js-tagsearch-file Box--responsive" data-tagsearch-path="Исследование_объявлений_о_продаже_квартир/README.md" data-tagsearch-lang="Markdown">
<div class="Box-body px-5 pb-5" data-target="readme-toc.content">
<article class="markdown-body entry-content container-lg">
<h2><strong>Описание проекта</strong></h2>
<div class="paragraph">Вы &mdash; маркетинговый аналитик развлекательного приложения Procrastinate Pro+. Несмотря на огромные вложения в рекламу, последние несколько месяцев компания терпит убытки. Ваша задача &mdash; разобраться в причинах и помочь компании выйти в плюс.</div>
<div class="paragraph">Есть данные о пользователях, привлечённых с&nbsp;1&nbsp;мая по 27&nbsp;октября 2019&nbsp;года:</div>
<ul>
<li>лог сервера с данными об их посещениях,</li>
<li>выгрузка их покупок за этот период,</li>
<li>рекламные расходы.</li>
</ul>
<div class="paragraph">Вам предстоит изучить:</div>
<ul>
<li>откуда приходят пользователи и какими устройствами они пользуются,</li>
<li>сколько стоит привлечение пользователей из различных рекламных каналов;</li>
<li>сколько денег приносит каждый клиент,</li>
<li>когда расходы на привлечение клиента окупаются,</li>
<li>какие факторы мешают привлечению клиентов.</li>
</ul>
<h2>Описание данных</h2>
<div class="paragraph">В вашем распоряжении три датасета. Файл <code class="code-inline code-inline_theme_light">visits_info_short.csv</code> хранит лог сервера с информацией о посещениях сайта, <code class="code-inline code-inline_theme_light">orders_info_short.csv</code>&nbsp;&mdash; информацию о заказах, а <code class="code-inline code-inline_theme_light">costs_info_short.csv</code>&nbsp;&mdash; информацию о расходах на рекламу.</div>
<div class="paragraph">Структура <code class="code-inline code-inline_theme_light">visits_info_short.csv</code>:</div>
<ul>
<li><code class="code-inline code-inline_theme_light">User Id</code> &mdash; уникальный идентификатор пользователя,</li>
<li><code class="code-inline code-inline_theme_light">Region</code> &mdash; страна пользователя,</li>
<li><code class="code-inline code-inline_theme_light">Device</code> &mdash; тип устройства пользователя,</li>
<li><code class="code-inline code-inline_theme_light">Channel</code> &mdash; идентификатор источника перехода,</li>
<li><code class="code-inline code-inline_theme_light">Session Start</code> &mdash; дата и время начала сессии,</li>
<li><code class="code-inline code-inline_theme_light">Session End</code> &mdash; дата и время окончания сессии.</li>
</ul>
<div class="paragraph">Структура&nbsp;<code class="code-inline code-inline_theme_light">orders_info_short.csv</code>:</div>
<ul>
<li><code class="code-inline code-inline_theme_light">User Id</code> &mdash; уникальный идентификатор пользователя,</li>
<li><code class="code-inline code-inline_theme_light">Event Dt</code> &mdash; дата и время покупки,</li>
<li><code class="code-inline code-inline_theme_light">Revenue</code> &mdash; сумма заказа.</li>
</ul>
<div class="paragraph">Структура&nbsp;<code class="code-inline code-inline_theme_light">costs_info_short.csv</code>:</div>
<ul>
<li><code class="code-inline code-inline_theme_light">dt</code>&nbsp;&mdash; дата проведения рекламной кампании,</li>
<li><code class="code-inline code-inline_theme_light">Channel</code> &mdash; идентификатор рекламного источника,</li>
<li><code class="code-inline code-inline_theme_light">costs</code> &mdash; расходы на эту кампанию.</li>
</ul>
<h2>Инструкция по выполнению проекта</h2>
<div class="paragraph">Рекомендуем ещё раз просмотреть урок &laquo;Разбор кейса&raquo; из темы &laquo;Юнит-экономика&raquo; перед началом работы.</div>
<h3><strong>Шаг 1. Загрузите данные и подготовьте их к анализу</strong></h3>
<div class="paragraph">Загрузите данные о визитах, заказах и рекламных расходах из CSV-файлов в переменные.</div>
<div class="paragraph"><strong>Пути к файлам</strong></div>
<ul>
<li>
<div class="paragraph"><code class="code-inline code-inline_theme_light">/datasets/visits_info_short.csv</code>. <a href="https://code.s3.yandex.net/datasets/visits_info_short.csv" target="_blank" rel="noopener">Скачать датасет</a>;</div>
</li>
<li>
<div class="paragraph"><code class="code-inline code-inline_theme_light">/datasets/orders_info_short.csv</code>. <a href="https://code.s3.yandex.net/datasets/orders_info_short.csv" target="_blank" rel="noopener">Скачать датасет</a>;</div>
</li>
<li>
<div class="paragraph"><code class="code-inline code-inline_theme_light">/datasets/costs_info_short.csv</code>. <a href="https://code.s3.yandex.net/datasets/costs_info_short.csv" target="_blank" rel="noopener">Скачать датасет</a>.</div>
</li>
</ul>
<div class="paragraph">Изучите данные и выполните предобработку. Есть ли в данных пропуски и дубликаты? Убедитесь, что типы данных во всех колонках&nbsp;соответствуют сохранённым в них значениям. Обратите внимание на столбцы с датой и временем.</div>
<h3><strong>Шаг 2. Задайте функции для расчёта и анализа LTV, ROI, удержания и конверсии.</strong></h3>
<div class="paragraph">Разрешается использовать функции, с которыми вы познакомились в теоретических уроках.</div>
<div class="paragraph">Это функции для вычисления значений метрик:</div>
<ul>
<li><code class="code-inline code-inline_theme_light">get_profiles()</code> &mdash; для создания профилей пользователей,</li>
<li><code class="code-inline code-inline_theme_light">get_retention()</code> &mdash; для подсчёта Retention Rate,</li>
<li><code class="code-inline code-inline_theme_light">get_conversion()</code> &mdash; для подсчёта конверсии,</li>
<li><code class="code-inline code-inline_theme_light">get_ltv()</code> &mdash; для подсчёта LTV.</li>
</ul>
<div class="paragraph">А также функции для построения графиков:</div>
<ul>
<li><code class="code-inline code-inline_theme_light">filter_data()</code> &mdash; для сглаживания данных,</li>
<li><code class="code-inline code-inline_theme_light">plot_retention()</code> &mdash; для построения графика Retention Rate,</li>
<li><code class="code-inline code-inline_theme_light">plot_conversion()</code> &mdash; для построения графика конверсии,</li>
<li><code class="code-inline code-inline_theme_light">plot_ltv_roi</code> &mdash; для визуализации LTV и ROI.</li>
</ul>
<h3><strong>Шаг 3. Исследовательский анализ данных</strong></h3>
<ul>
<li>Составьте профили пользователей. Определите минимальную и максимальную даты привлечения пользователей.</li>
<li>Выясните, из каких стран пользователи приходят в приложение и на какую страну приходится больше всего платящих пользователей. Постройте таблицу, отражающую количество пользователей и долю платящих из каждой страны.</li>
<li>Узнайте, какими устройствами пользуются клиенты и какие устройства предпочитают платящие пользователи. Постройте таблицу, отражающую количество пользователей и долю платящих для каждого устройства.</li>
<li>Изучите рекламные источники привлечения и определите каналы, из которых пришло больше всего платящих пользователей. Постройте таблицу, отражающую количество пользователей и долю платящих для каждого канала привлечения.</li>
</ul>
<div class="paragraph">После каждого пункта сформулируйте выводы.</div>
<h3>Шаг 4. Маркетинг</h3>
<ul>
<li>Посчитайте общую сумму расходов на маркетинг.</li>
<li>Выясните, как траты распределены по рекламным источникам, то есть сколько денег потратили на каждый источник.</li>
<li>Постройте визуализацию динамики изменения расходов во времени (по неделям и месяцам) по каждому источнику. Постарайтесь отразить это на одном графике.</li>
<li>Узнайте, сколько в среднем стоило привлечение одного пользователя (CAC) из каждого источника. Используйте профили пользователей.</li>
</ul>
<div class="paragraph">Напишите промежуточные выводы.</div>
<h3>Шаг 5. Оцените окупаемость рекламы</h3>
<div class="paragraph">Используя графики LTV, ROI и CAC, проанализируйте окупаемость рекламы. Считайте, что на календаре 1 ноября 2019 года, а в бизнес-плане заложено, что пользователи должны окупаться не позднее чем через две недели после привлечения. Необходимость включения в анализ органических пользователей определите самостоятельно.</div>
<ul>
<li>Проанализируйте окупаемость рекламы c помощью графиков LTV и ROI, а также графики динамики LTV, CAC и ROI.</li>
<li>Проверьте конверсию пользователей и динамику её изменения. То же самое сделайте с удержанием пользователей. Постройте и изучите графики конверсии и удержания.</li>
<li>Проанализируйте окупаемость рекламы с разбивкой по устройствам. Постройте графики LTV и ROI, а также графики динамики LTV, CAC и ROI.</li>
<li>Проанализируйте окупаемость рекламы с разбивкой по странам. Постройте графики LTV и ROI, а также графики динамики LTV, CAC и ROI.</li>
<li>Проанализируйте окупаемость рекламы с разбивкой по рекламным каналам. Постройте графики LTV и ROI, а также графики динамики LTV, CAC и ROI.</li>
<li>Ответьте на такие вопросы:
<ul>
<li>Окупается ли реклама, направленная на привлечение пользователей в целом?</li>
<li>Какие устройства, страны и рекламные каналы могут оказывать негативное влияние на окупаемость рекламы?</li>
<li>Чем могут быть вызваны проблемы окупаемости?</li>
</ul>
</li>
</ul>
<div class="paragraph">Напишите вывод, опишите возможные причины обнаруженных проблем и промежуточные рекомендации для рекламного отдела.</div>
<h3>Шаг 6. Напишите выводы</h3>
<ul>
<li>Выделите причины неэффективности привлечения пользователей.</li>
<li>Сформулируйте рекомендации для отдела маркетинга.</li>
</ul>
</article>
</div>
</div>
</div>
</div>
</div>
