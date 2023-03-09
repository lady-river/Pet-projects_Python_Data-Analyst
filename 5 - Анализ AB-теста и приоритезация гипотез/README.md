<div class="application-main " data-commit-hovercards-enabled="" data-discussion-hovercards-enabled="" data-issue-and-pr-hovercards-enabled="">
<div class="">
<div class="clearfix container-xl px-3 px-md-4 px-lg-5 mt-4">
<div id="readme" class="Box md js-code-block-container js-code-nav-container js-tagsearch-file Box--responsive" data-tagsearch-path="Исследование_объявлений_о_продаже_квартир/README.md" data-tagsearch-lang="Markdown">
<div class="Box-body px-5 pb-5" data-target="readme-toc.content">
<article class="markdown-body entry-content container-lg">
<h2>Описание данных</h2>
<div class="paragraph"><strong>Данные для первой части</strong></div>
<ul>
<li><code class="code-inline code-inline_theme_light">Hypothesis</code> &mdash; краткое описание гипотезы;</li>
<li><code class="code-inline code-inline_theme_light">Reach</code> &mdash; охват пользователей по 10-балльной шкале;</li>
<li><code class="code-inline code-inline_theme_light">Impact</code> &mdash; влияние на пользователей по 10-балльной шкале;</li>
<li><code class="code-inline code-inline_theme_light">Confidence</code> &mdash; уверенность в гипотезе по 10-балльной шкале;</li>
<li><code class="code-inline code-inline_theme_light">Efforts</code> &mdash; затраты ресурсов на проверку гипотезы по 10-балльной шкале. Чем больше значение <code class="code-inline code-inline_theme_light">Efforts</code>, тем дороже проверка гипотезы.</li>
</ul>
<div class="paragraph"><strong>Данные для второй части</strong></div>
<ul>
<li><code class="code-inline code-inline_theme_light">transactionId</code> &mdash; идентификатор заказа;</li>
<li><code class="code-inline code-inline_theme_light">visitorId</code> &mdash; идентификатор пользователя, совершившего заказ;</li>
<li><code class="code-inline code-inline_theme_light">date</code> &mdash; дата, когда был совершён заказ;</li>
<li><code class="code-inline code-inline_theme_light">revenue</code> &mdash; выручка заказа;</li>
<li><code class="code-inline code-inline_theme_light">group</code> &mdash; группа A/B-теста, в которую попал заказ.</li>
</ul>
<ul>
<li><code class="code-inline code-inline_theme_light">date</code> &mdash; дата;</li>
<li><code class="code-inline code-inline_theme_light">group</code> &mdash; группа A/B-теста;</li>
<li><code class="code-inline code-inline_theme_light">visitors</code> &mdash; количество пользователей в указанную дату в указанной группе A/B-теста</li>
</ul>
<h2>Описание проекта</h2>
<h3>Контекст</h3>
<div class="paragraph">Вы &mdash; аналитик крупного интернет-магазина. Вместе с отделом маркетинга вы подготовили список гипотез для увеличения выручки.</div>
<div class="paragraph">Приоритизируйте гипотезы, запустите A/B-тест и проанализируйте результаты.</div>
<h3>Часть 1. Приоритизация гипотез.</h3>
<div class="paragraph">В файле <code class="code-inline code-inline_theme_light">/datasets/hypothesis.csv</code> 9 гипотез по увеличению выручки интернет-магазина с указанными параметрами <code class="code-inline code-inline_theme_light">Reach</code>, <code class="code-inline code-inline_theme_light">Impact</code>, <code class="code-inline code-inline_theme_light">Confidence</code>, <code class="code-inline code-inline_theme_light">Effort</code>.</div>
<div class="paragraph"><strong>Задача</strong></div>
<ul>
<li>Примените фреймворк <code class="code-inline code-inline_theme_light">ICE</code> для приоритизации гипотез. Отсортируйте их по убыванию приоритета.</li>
<li>Примените фреймворк <code class="code-inline code-inline_theme_light">RICE</code> для приоритизации гипотез. Отсортируйте их по убыванию приоритета.</li>
<li>Укажите, как изменилась приоритизация гипотез при применении <code class="code-inline code-inline_theme_light">RICE</code> вместо <code class="code-inline code-inline_theme_light">ICE</code>. Объясните, почему так произошло.</li>
</ul>
<h3>Часть 2. Анализ A/B-теста</h3>
<div class="paragraph">Вы провели A/B-тест и получили результаты, которые описаны в файлах <code class="code-inline code-inline_theme_light">/datasets/orders.csv</code> и <code class="code-inline code-inline_theme_light">/datasets/visitors.csv</code>.</div>
<div class="paragraph"><strong>Задача</strong></div>
<div class="paragraph">Проанализируйте A/B-тест:</div>
<ol start="1">
<li>Постройте график кумулятивной выручки по группам. Сделайте выводы и предположения.</li>
<li>Постройте график кумулятивного среднего чека по группам. Сделайте выводы и предположения.</li>
<li>Постройте график относительного изменения кумулятивного среднего чека группы B к группе A. Сделайте выводы и предположения.</li>
<li>Постройте график кумулятивного среднего количества заказов на посетителя по группам. Сделайте выводы и предположения.</li>
<li>Постройте график относительного изменения кумулятивного среднего количества заказов на посетителя группы B к группе A. Сделайте выводы и предположения.</li>
<li>Постройте точечный график количества заказов по пользователям. Сделайте выводы и предположения.</li>
<li>Посчитайте 95-й и 99-й перцентили количества заказов на пользователя. Выберите границу для определения аномальных пользователей.</li>
<li>Постройте точечный график стоимостей заказов. Сделайте выводы и предположения.</li>
<li>Посчитайте 95-й и 99-й перцентили стоимости заказов. Выберите границу для определения аномальных заказов.</li>
<li>Посчитайте статистическую значимость различий в среднем количестве заказов на посетителя между группами по &laquo;сырым&raquo; данным. Сделайте выводы и предположения.</li>
<li>Посчитайте статистическую значимость различий в среднем чеке заказа между группами по &laquo;сырым&raquo; данным. Сделайте выводы и предположения.</li>
<li>Посчитайте статистическую значимость различий в среднем количестве заказов на посетителя между группами по &laquo;очищенным&raquo; данным. Сделайте выводы и предположения.</li>
<li>Посчитайте статистическую значимость различий в среднем чеке заказа между группами по &laquo;очищенным&raquo; данным. Сделайте выводы и предположения.</li>
<li>Примите решение по результатам теста и объясните его. Варианты решений: 1. Остановить тест, зафиксировать победу одной из групп. 2. Остановить тест, зафиксировать отсутствие различий между группами. 3. Продолжить тест.</li>
</ol>
</article>
</div>
</div>
</div>
</div>
</div>
