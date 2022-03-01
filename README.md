# lab01_timp
ОТЧЁТ.

ПУНКТ 1.
Установка библиотеки boost с помощью утилиты wget
wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz

ПУНКТ 2.
Разархивация скаченного файла в директорию ~/boost_1_69_0
tar -x boost_1_69_0.tar.gz

ПУНКТ 3.
Подсчёт количества файлов в директории ~/boost_1_69_0 не включая вложенные директории.
ls | wc -l
<img width="1440" alt="1" src="https://user-images.githubusercontent.com/91692911/155755130-cc3913c2-73c1-4702-8544-31dd5197ab4e.png">

ПУНКТ 4.
Подсчёт количества файлов в директории ~/boost_1_69_0 включая вложенные директории.
find . -type f | wc -l

ПУНКТ 5.
Подсчёт количества заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp).
find . -type f '!' -name '*.cpp' | wc -l 
<img width="1440" alt="3" src="https://user-images.githubusercontent.com/91692911/155758343-9c3e71f3-e2cd-4362-9a89-45043d773184.png">

ПУНКТ 6.
Найти полный пусть до файла any.hpp внутри библиотеки boost.
find . -type f -name "any.hpp"
<img width="1440" alt="4" src="https://user-images.githubusercontent.com/91692911/155759464-28df5d87-cf28-47c2-b985-d82446f4ba8f.png">

ПУНКТ 7.
Вывести в консоль все файлы, где упоминается последовательность boost::asio
boost_1_69_0 % grep -rl "boost::asio" . (//Вывод после выполнения большой, на скриншоте приведена часть файлов)
<img width="1440" alt="5" src="https://user-images.githubusercontent.com/91692911/155760506-ab5c0cb7-f636-4399-8edb-5a98022a4c1b.png">

ПУНКТ 8.
Скомпилировать boost.
./bootstrap.sh --prefix=boost_output
./b2 install

ПУНКТ 9.
Перенести все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs.
mv boost_1_69_0/boost_output ~/boost-libs
 
 ПУНКТ 10.
 Подсчитать, сколько занимает дискового пространства каждый файл в этой директории.
ls -s 
![1](https://user-images.githubusercontent.com/91692911/155890552-6daaa327-f6c2-4ffc-a490-99dad415a126.png)


 ПУНКТ 11.
 Найти топ10 самых "тяжёлых".
 ls -sh -S
 ![2](https://user-images.githubusercontent.com/91692911/155890557-c93837b2-d463-4cf1-ade0-1ca24a71abea.png)

  
