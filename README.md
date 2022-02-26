# lab01_timp
ОТЧЁТ.

ПУНКТ 1.
Установка библиотеки boost с помощью утилиты wget
wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz

ПУНКТ 2.
Разархивация скаченного файла в директорию ~/boost_1_69_0
tar -xf boost_1_69_0.tar.gz

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
du -h .
<img width="1440" alt="1" src="https://user-images.githubusercontent.com/91692911/155845697-21549f7a-a7e5-4bfe-a192-5261c19e2491.png">

 ПУНКТ 11.
 Найти топ10 самых "тяжёлых".
 <img width="1440" alt="1" src="https://user-images.githubusercontent.com/91692911/155851196-8dfb85f1-c27d-49b0-9944-dd91d1c8f2d5.png">
 du -h . | sort -rh  | head -n 10
 
  
