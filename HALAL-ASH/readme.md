<p align="center">
  <b>JMeter script for testing www.halal-ash.ru website</b>
</p>
<p align="center">
  <b>Скрипт JMeter по тестированию сайта www.halal-ash.ru</b>
</p>

<b>Действия</b>
1. Авторизация на сайте
2. Рандомный выбор id подкаталога на главной странице
3. Рандомный выбор id товара на странице подкаталога
4. Добавление в корзину, выбранного id товара. 
   Добавление товара M раз, где M - рандомное количество от 1 до 3
5. Выбор id товара в корзине рандомным способом
6. Удаление из корзины, выбранного id товара.
   Удаление товара N раз, где N - рандомное количество от 1 до 2
7. Выход из системы

<b>Примечание:</b>
</p>
Как видно из <b>Response Body 2-02.Main page</b>, каталог "<b>Казы из конины</b>" - "icon14", имеет "0" наименований.
</p>
Поэтому, при рандомном выборе id="icon14", заменяем "icon14" ( "2-00. JSR223 PostProcessor. Выбор id_catalog") на подобный каталог id="icon5" - "<b>Мясные деликатесы</b>" у которого "35" наменований .</p>
<b>Response Body 2-02.Main page</b>: </p>
id="icon14" href="/catalog/kazy_iz_koniny/" > 		<span>&nbsp;</span><b>Казы из конины</b><font>0 наименований</font></p>
id="icon5" href="/catalog/myasnye-delikatesy/" > 		<span>&nbsp;</span><b>Мясные деликатесы</b><font>35 наименований</font>

<p
</p>

<b>Actions</b>
1. Authorization on the website
2. Randomly selecting a subcategory ID on the main page
3. Randomly selecting a product ID on the subcategory page
4. Adding the selected product to the shopping cart.
   Adding the product M times, where M is a random number from 1 to 3
5. Randomly selecting a product ID in the shopping cart
5. Removing the selected product ID from the shopping cart
6. Removing the selected product from the cart.
   Removing the product N times, where N is a random number from 1 to 2
6. Logging out of the system
<p
</p>

Here we can see <b>Aggregate Report</b>
![Aggregate Report](Test_Results/1.aggregate_report.png?raw=true "Title")

Here we can see how many <b>transactions per second</b> are done in lapse of time
![Transactions per second](Test_Results/2.transactions_per_second.png?raw=true "Title")

Here we can see <b>responses in lapse of time</b>
![Response times over time](Test_Results/3.response_times_over_time.png?raw=true "Title")

</p>
В HTTP Request (запрос) установлен параметр <b>Retrieve all embedded resources</b> для полноценной имитации браузера и получения всех ресурсов со страницы запроса.
</p>

Here we can see <b>active users (threads) in lapse of time</b>
![Active threads over time](Test_Results/4.active_threads_over_time.png?raw=true "Title")

<b>Ограничения:</b>
</p>
Задано краткосрочное время на ступени нагрузки, чтобы снизить риск блокировки внешним сервисом.
Фактически, рекомендуется время на ступени нагрузки устанавливать 20 мин.
</p>