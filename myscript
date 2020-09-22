#ЛАБОРАТОРНАЯ РАБОТА МАГНА (6-7 РПП)

#####################
#I. Базовые скрипты #
#####################

#1 Определение текущей директории и текущего пользователя
!/bin/bash
echo "The current directory is:"
pwd
echo "The user logged in is:"
whoami

#2 Вывод домашней директории текущего пользователя
!/bin/bash
echo "Home for the current user is: $HOME"

#3 Управляющие последовательности
!/bin/bash
echo "I have \$1 in my pocket"

#4 Пользовательские переменные
!/bin/bash
 testing variables
grade=5
person="Adam"
echo "$person is a good boy, he is in grade $grade"

#5 Вывод переменной-результата работы команды
!/bin/bash
mydir=$(pwd)
echo $mydir

#6 Арифметические операции
!/bin/bash
var1=$(( 5 + 5 ))
echo $var1
var2=$(( $var1 * 2 ))
echo $var2

#7 Простое условие
!/bin/bash
if pwd
then
echo "It works"
fi

#8 Проверка существования текущего пользователя
!/bin/bash
user=delamart
if grep $user /etc/passwd
then
echo "The user $user Exists"
fi

#9 Проверка существования несуществующего пользователя
!/bin/bash
user=anotherUser
if grep $user /etc/passwd
then
echo "The user $user Exists"
else
echo "The user $user doesn’t exist"
fi

#10 Проверка существования пользователя с указанием директории
!/bin/bash
user=anotherUser
if grep $user /etc/passwd
then
echo "The user $user Exists"
elif ls /home
then
echo "The user doesn’t exist but anyway there is a directory under /home"
fi

#11 Сравнение чисел
!/bin/bash
val1=6
if [ $val1 -gt 5 ]
then
echo "The test value $val1 is greater than 5"
else
echo "The test value $val1 is not greater than 5"
fi

#12 Сравнение строк
!/bin/bash
val1=text
val2="something_else"
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi

#13 Сравнение строк-имен пользователя
!/bin/bash
user="delamart"
if [ $user = $USER ]
then
echo "The user $user is the current logged in user"
fi

#14 Сравнение строк с сортировкой файла
!/bin/bash
val1=Delamart
val2=delamart
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi

#15 Проверка существования директории
!/bin/bash
mydir=/home/delamart
if [ -d $mydir ]
then
echo "The $mydir directory exists"
cd $ mydir
ls
else
echo "The $mydir directory does not exist"
fi

######################
#II. Циклы в скриптах# 
######################

#16 Простой цикл
!/bin/bash
for var in first second third fourth fifth
do
echo The  $var item
done

#17 Цикл перебора сложных значений
!/bin/bash
for var in first "the second" "the third" "I’ll do it"
do
echo "This is: $var"
done

#18 Цикл по списку-результату команды
!/bin/bash
file="myfile"
for var in $(cat $file)
do
echo " $var"
done

#18.5 Игнорирование разделителя полей
!/bin/bash
file="/etc/passwd"
IFS=$'\n'
for var in $(cat $file)
do
echo " $var"
done

#19 Обход файлов в директории
!/bin/bash
for file in /home/delamart/*
do
if [ -d "$file" ]
then
echo "$file is a directory"
elif [ -f "$file" ]
then
echo "$file is a file"
fi
done

#20 Цикл в стиле C вывести числа от 1 до 10
!/bin/bash
for (( i=1; i <= 10; i++ ))
do
echo "number is $i"
done

#21 Цикл while
!/bin/bash
var1=5
while [ $var1 -gt 0 ]
do
echo $var1
var1=$[ $var1 - 1 ]
done

#22 Вложенный цикл
!/bin/bash
for (( a = 1; a <= 3; a++ ))
do
echo "Start $a:"
for (( b = 1; b <= 3; b++ ))
do
echo " Inner loop: $b"
done
done

#22.5 Обработка содержимого файла
!/bin/bash
IFS=$'\n'
for entry in $(cat /etc/passwd)
do
echo "Values in $entry –"
IFS=:
for value in $entry
do
echo " $value"
done
done

#23 Управление циклами, break
!/bin/bash
for var1 in 1 2 3 4 5 6 7 8 9 10
do
if [ $var1 -eq 5 ]
then
break
fi
echo "Number: $var1"
done

#24 Управление циклами, break для while
!/bin/bash
var1=1
while [ $var1 -lt 10 ]
do
if [ $var1 -eq 5 ]
then
break
fi
echo "Iteration: $var1"
var1=$(( $var1 + 1 ))
done

#25 Управление циклами, continue
!/bin/bash
for (( var1 = 1; var1 < 15; var1++ ))
do
if [ $var1 -gt 5 ] && [ $var1 -lt 10 ]
then
continue
fi
echo "Iteration number: $var1"
done

#26 Обработка вывода в цикле
!/bin/bash
for (( a = 1; a < 10; a++ ))
do
echo "Number is $a"
done > myfile.txt
echo "finished."

#27 Список исполняемых файлов из PATH
!/bin/bash
IFS=:
for folder in $PATH
do
echo "$folder:"
for file in $folder/*
do
if [ -x $file ]
then
echo " $file"
fi
done
done

#############################
#III. Ключи командной строки#
#############################

#28 Параметры командной строки 5 10 15
!/bin/bash
echo $0
echo $1
echo $2
echo $3

#29 Сумма чисел через параметры 14 88
!/bin/bash
total=$[ $1 + $2 ]
echo The first parameter is $1.
echo The second parameter is $2.
echo The sum is $total.

#30 Параметр - имя
!/bin/bash
echo Hello $1, how do you do

#31 Проверка параметров
!/bin/bash
if [ -n "$1" ]
then
echo Hello $1.
else
echo "No parameters found. "
fi

#32 Подсчет параметров
!/bin/bash
echo There were $ parameters passed.

#33 Получить последний параметр
!/bin/bash
echo The last parameter was ${!}

#34 Захват все параметров
!/bin/bash
echo "Using the \$* method: $*"
echo "-----------"
echo "Using the \$@ method: $@"

#35 Проход по параметрам в цикле
!/bin/bash
count=1
for param in "$*"
do
echo "\$* Parameter $count = $param"
count=$(( $count + 1 ))
done
count=1
for param in "$@"
do
echo "\$@ Parameter $count = $param"
count=$(( $count + 1 ))
done

#36 Команда сдвига параметров shift
!/bin/bash
count=1
while [ -n "$1" ]
do
echo "Parameter $count = $1"
count=$(( $count + 1 ))
shift
done

#37 Ключи командной строки
!/bin/bash
echo
while [ -n "$1" ]
do
case "$1" in
-a) echo "Found the -a option" ;;
-b) echo "Found the -b option" ;;
-c) echo "Found the -c option" ;;
*) echo "$1 is not an option" ;;
esac
shift
done

#38 Список ключей оканчивается --, а далее идут параметры
!/bin/bash
while [ -n "$1" ]
do
case "$1" in
-a) echo "Found the -a option" ;;
-b) echo "Found the -b option" ;;
-c) echo "Found the -c option" ;;
--) shift
break ;;
*) echo "$1 is not an option";;
esac
shift
done
count=1
for param in $@
do
echo "Parameter $count: $param"
count=$(( $count + 1 ))
done

#39 Обработка ключей со значениями
!/bin/bash
while [ -n "$1" ]
do
case "$1" in
-a) echo "Found the -a option";;
-b) param="$2"
echo "Found the -b option, with parameter value $param"
shift ;;
-c) echo "Found the -c option";;
--) shift
break ;;
*) echo "$1 is not an option";;
esac
shift
done
count=1
for param in "$@"
do
echo "Parameter $count: $param"
count=$(( $count + 1 ))
done

#40 Использование стандартных ключей, ввод имени
!/bin/bash
echo -n "Enter your name: "
read name
echo "Hello $name, welcome to my program."

#41 Ввод имени и фамилии
!/bin/bash
read -p "Enter your name: " first last
echo "Your data for $last, $first…"

#42 Использование переменной reply
!/bin/bash
read -p "Enter your name: "
echo Hello $REPLY, welcome to my program.

#43 Ввод с ожиданием в секундах
!/bin/bash
if read -t 5 -p "Enter your name: " name
then
echo "Hello $name, welcome to my script"
else
echo "Sorry, too slow! "
fi

#44 Ввод пароля
!/bin/bash
read -s -p "Enter your password: " pass
echo "Is your password really $pass? "

#45 Чтение файла
!/bin/bash
count=1
cat myfile1 | while read line
do
echo "Line $count: $line"
count=$(( $count + 1 ))
done
echo "Finished"

##################
#IV. Ввод и вывод# 
##################

#47 Приписать путь в файл
pwd >> myfile.txt
cat myfile.txt

#48 Записать ошибку в существующий файл
ls -l xfile 2>myfile.txt
cat myfile.txt

#49 Скрипт перенаправления вывода
!/bin/bash
echo "This is an error" >&2
echo "This is normal output
 Перенаправить ошибки в файл
bash myscript 2> myfile
cat content

#50 Перенаправление в декскриптор комнадой exec
!/bin/bash
exec 1>outfile
echo "This is a test of redirecting all output"
echo "from a shell script to another file."
echo "without having to redirect every line"

#51 Использование exec в начале скрипта
!/bin/bash
exec 2>myerror
echo "This is the start of the script"
echo "now redirecting all output to another location"
exec 1>myfile
echo "This should go to the myfile file"
echo "and this should go to the myerror file" >&2

#52 Перенаправление ввода в скриптах
!/bin/bash
exec 0< myfile
count=1
while read line
do
echo "Line $count: $line"
count=$(( $count + 1 ))
done

#53 Создание кастомного перенаправления вывода
!/bin/bash
exec 3>myfile
echo "This should display on the screen"
echo "and this should be stored in the file" >&3
echo "And this should be back on the screen"

#54 Создание дескриптора для ввода данных
!/bin/bash
exec 6<&0
exec 0< myfile
count=1
while read line
do
echo "Line $count: $line"
count=$(( $count + 1 ))
done
exec 0<&6
read -p "Are you done now? " answer
case $answer in
y) echo "Goodbye";;
n) echo "Sorry, this is the end.";;
esac

#55 Закрытие дескрипторов файлов
!/bin/bash
exec 3> myfile
echo "This is a test line of data" >&3
exec 3>&-
echo "This won't work" >&3

#56 Получение сведений об открытых дескрипторах командой lsof
!/bin/bash
exec 3> myfile1
exec 6> myfile2
exec 7< myfile3
lsof -a -p $$ -d 0,1,2,3,6,7

##################################################
#V. Сигналы, фоновые задачи, управление скриптами#
##################################################

#57 Перехват сигналов
!/bin/bash
trap "echo ' Trapped Ctrl-C'" SIGINT
echo This is a test script
count=1
while [ $count -le 10 ]
do
echo "Loop $count"
sleep 1
count=$(( $count + 1 ))
done

#58 Перехват сигнала выхода из скрипта EXIT
!/bin/bash
trap "echo Goodbye..." EXIT
count=1
while [ $count -le 5 ]
do
echo "Loop $count"
sleep 1
count=$(( $count + 1 ))
done

#59 Модификация сигналов и отмена перехвата
!/bin/bash
trap "echo 'Ctrl-C is trapped.'" SIGINT
count=1
while [ $count -le 5 ]
do
echo "Loop $count"
sleep 1
count=$(( $count + 1 ))
done
trap "echo ' I modified the trap!'" SIGINT
count=1
while [ $count -le 5 ]
do
echo "Second Loop $count"
sleep 1
count=$(( $count + 1 ))
done

#60 Отмена перехвата сигнала
!/bin/bash
trap "echo 'Ctrl-C is trapped.'" SIGINT
count=1
while [ $count -le 5 ]
do
echo "Loop $count"
sleep 1
count=$(( $count + 1 ))
done
trap -- SIGINT
echo "I just removed the trap"
count=1
while [ $count -le 5 ]
do
echo "Second Loop $count"
sleep 1
count=$(( $count + 1 ))
done

#61 Выполнение скрипта в фоновом режиме (указать & параметром)
!/bin/bash
count=1
while [ $count -le 10 ]
do
sleep 1
count=$(( $count + 1 ))
done

#62 Выполнение скрипта после закрытия терминала
nohup bash myscript &

#63 Просмотр заданий
!/bin/bash
count=1
while [ $count -le 10 ]
do
echo "Loop $count"
sleep 10
count=$(( $count + 1 ))
done

#64 Перезапуск приостановленных заданий
bg
fg

#65 Планирование запуска скриптов
sudo apt install at
at -f myscript now

#65.5 Список заданий, ожидающих выполнения и их удаление
atq
atrm

#####################################
#VI. Функции и разработка библиотек.# 
#####################################

#66 Скрипт объявления функции и ее использования
!/bin/bash
function myfunc {
echo "This is an example of using a function"
}
count=1
while [ $count -le 3 ]
do
myfunc
count=$(( $count + 1 ))
done
echo "This is the end of the loop"
myfunc
echo "End of the script"

#67 Цикличный вызов функции - доказательство некорректности
!/bin/bash
count=1
while [ $count -le 3 ]
do
myfunc
count=$(( $count + 1 ))
done
echo "This is the end of the loop"
function myfunc {
echo "This is an example of using a function"
}
echo "End of the script"

#68 Вызов двух одноименных функций
!/bin/bash
function myfunc {
echo "The first function definition"
}
myfunc
function myfunc {
echo "The second function definition"
}
myfunc
echo "End of the script"

#69 Использование return
!/bin/bash
function myfunc {
read -p "Enter a value: " value
echo "adding value"
return $(( $value + 10 ))
}
myfunc
echo "The new value is $?"

#70 Запись вывод функции в переменную
!/bin/bash
function myfunc {
read -p "Enter a value: " value
echo $(( $value + 10 ))
}
result=$( myfunc)
echo "The value is $result"

#71 Аргументы функций
!/bin/bash
function addnum {
if [ $ -eq 0 ] || [ $ -gt 2 ]
then
echo -1
elif [ $ -eq 1 ]
then
echo $(( $1 + $1 ))
else
echo $(( $1 + $2 ))
fi
}
echo -n "Adding 10 and 15: "
value=$(addnum 10 15)
echo $value
echo -n "Adding one number: "
value=$(addnum 10)
echo $value
echo -n "Adding no numbers: "
value=$(addnum)
echo $value
echo -n "Adding three numbers: "
value=$(addnum 10 15 20)
echo $value

#72 Работа с параметрами напрямую
!/bin/bash
function myfunc {
echo $(( $1 + $2 ))
}
if [ $ -eq 2 ]
then
value=$(myfunc $1 $2)
echo "The result is $value"
else
echo "Usage: myfunc a b"
fi

#73 Глобальные переменные 
!/bin/bash
function myfunc {
value=$(( $value + 10 ))
}
read -p "Enter a value: " value
myfunc
echo "The new value is: $value"

74 Локальные переменные
!/bin/bash
function myfunc {
local temp=$[ $value + 5 ]
echo "The Temp from inside function is $temp"
}
temp=4
myfunc
echo "The temp from outside is $temp"

#75 Передача массивов в качестве аргументов, будет получен только 1 элемент
!/bin/bash
function myfunc {
echo "The parameters are: $@"
arr=$1
echo "The received array is ${arr[*]}"
}
myarray=(1 2 3 4 5)
echo "The original array is: ${myarray[*]}"
myfunc $myarray

#76 Передача всего массива
!/bin/bash
function myfunc {
local newarray
newarray=("$@")
echo "The new array value is: ${newarray[*]}"
}
myarray=(1 2 3 4 5)
echo "The original array is ${myarray[*]}"
myfunc ${myarray[*]}

#77 Рекурсивные функции, поиск факториала
!/bin/bash
function factorial {
if [ $1 -eq 1 ]
then
echo 1
else
local temp=$(( $1 - 1 ))
local result=$(factorial $temp)
echo $(( $result * $1 ))
fi
}
read -p "Enter value: " value
result=$(factorial $value)
echo "The factorial of $value is: $result"

#78 Создание и использование библиотек
!/bin/bash
. ./myfuncs
result=$(addnum 10 20)
echo "The result is: $result"

##############################
#VII. Sed и обработка текстов# 
##############################

#79 Простой вызов
echo "This is a test" | sed 's/test/another test/'

#80 Чтение команд из файла
sed -f mycommands myfile

#81 Флаги команды замены
sed 's/test/another test/' myfile

#82 Удаление строк из файла в интервале
sed '2,3d' myfile

#83 Удаление строк из файла от заданного и до конца
sed '3,$d' myfile

#84 Вставка текста в поток
echo "Another test" | sed 'i\First test '

#85 Вставка строки по номеру в файл
sed '2i\This is the inserted line.' myfile

#86 Замена строки в файле
sed '3c\This is a modified line.' myfile

#87 Вывод номеров строк
sed '=' myfile

#88 Вставка данных из другого файла
sed '3r newfile' myfile

##########################################
#VIII. AWK-скрипты, язык обработки данных# 
##########################################

#89 Вывод первого поля awk-скриптом
awk '{print $1}' myfile

#90 Тоже самое, но для passwd с игнором табуляции и тд
awk -F: '{print $1}' /etc/passwd

#91 Пример многострочной команды
echo "My name is Tom" | awk '{$4="Adam"; print $0}'

#92 Чтение скрипта из файла
{print $1 " has a  home directory at " $6}
awk -F: -f testfile /etc/passwd

#93 Выполнить команду до обработки файла
$ awk 'BEGIN {print "The File Contents:"}
{print $0}' myfile

#94 Выполнить команду после обработки файла
awk 'BEGIN {print "The File Contents:"}
{print $0}
END {print "End of File"}' myfile

#95 Обработка файла passwd
#Вызов: awk -f myscript  /etc/passwd
BEGIN {
print "The latest list of users and shells"
print " UserName \t HomePath"
print "-------- \t -------"
FS=":"
}
{
print $1 " \t " $6
}
END {
print "The end"
}

#96 Переменная ENIVRON
awk '
BEGIN{
print ENVIRON["HOME"]
print ENVIRON["PATH"]
}'

#97 Обращение к последнему полю записи с помощью NF
awk 'BEGIN{FS=":"; OFS=":"} {print $1,$NF}' /etc/passwd

#98 Пользовательские переменные в awk
awk '
BEGIN{
test="This is a test"
print test
}'

#99 Пример цикла while
awk '{
total = 0
i = 1
while (i < 4)
{
total += $i
i++
}
avg = total / 3
print "Average:",avg
}' myfile

#100 Пример цикла for
awk '{
total = 0
for (i = 1; i < 4; i++)
{
total += $i
}
avg = total / 3
print "Average:",avg
}' myfile