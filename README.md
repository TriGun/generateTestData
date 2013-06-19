Библиотека генерирует тестовые данные в таблицы.
-------------------------------------
###В чем прикол:
* Работает быстро. Сгенерировала 10 000 записей (12 полей, 2 поля из которых со связанных таблиц) за 12 секунд.
* Много (аж 15 штук) готовых паттернов для генерации.
* Можно легко расширять. Создать свою функцию в любом хелпере и ее название  передать в паттерн.  И все.
* Паттерн  имеет  читабельный вид. Похож на вызов php функции. Например text(1,10)
* В функцию генерации даты, даты можно передавать в любом формате (12-09-2012, 15-Jan-13 etc)
* Рандомно выбирает каринки из указанной папки. Функция img('path_to_dir')
* Выбирает данные из связанных таблиц. Фуекция table(table,field)
* Если  в связанной таблице закончились данные - генерация прекращаеться и пишеться столько, сколько сгенерилось по факту.
* Лекгая и быстрая либа(всего 331 строчка кода)

###Подключение 
-----------

	$this->load->library('gtd');
	
	 
 
###Генерация:
-----------

	$this->gtd->generate('table','50',array('field1'=>'int(1,10)'));
	

###Можно  вывести на экран, как будут выглядеть данные: 
-----------

	$this->gtd->test('table','50',array('field1'=>'int(1,10)'));

	
###Паттерны (аж 15 штук):
-----------
 * int(min,max) - целое число от min к max
 * double(min,max) - вещественное  число от min к max
 * do_array(array(1,'test',100)) - значение из массива
 * str(min,max) - строка размер которой от min до max
 * name() - имя
 * surname() - фамилия
 * fullname() - имя фамилия
 * address() - адрес
 * phone() - номер телефона
 * text(min,max) - текст от min до max
 * date(date_start,date_finish,pattern) - дата от date_start до date_finish.
 * url() - доменное имя
 * md5(123) - md5 от 123
 * img($path) - название картинки из папки $path(относительный путь)
 * table(table,field,isOne) - выбор данных из таблицы.

 Спасибо Санечку(trigalex)  и  Жеке Книжнику(Borsch) за помощь и умные мысли :)
