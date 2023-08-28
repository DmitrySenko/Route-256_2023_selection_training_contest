# Route-256 2023 selection test
Здесь собраны решения задач из тренировочного контеста, который давался на курс Junior Go-developper от Ozon. Частичное решение означает, что код работает слишком медленно для больших объемов данных.

## A. Сумматор (5 баллов)
Эта задача познакомит вас с тестирующей системой Codeforces. Правильные решения задач должны проходить все заранее заготовленные тесты жюри и укладываться в ограничения по времени/памяти на каждом тесте. Ниже перечислены технические требования к решениям:
* решение располагается в одном файле исходного кода;
* решение читает входные данные со стандартного ввода (клавиатуры);
* решение пишет выходные данные на стандартный вывод (экран);
* решение не взаимодействует как-либо с другими ресурсами компьтера (сеть, жесткий диск, процессы и прочее);
* решение использует только стандартную библиотеку языка;
* решение располагается в пакете по-умолчанию (или его аналоге для вашего языка), имеют стандартную точку входа для консольных программ;
* гарантируется, что во всех тестах выполняются все ограничения, что содержатся в условии задачи — как-либо проверять входные данные на корректность не надо, все тесты строго соответствуют описанному в задаче формату;
выводите ответ в точности в том формате, как написано в условии задачи (не надо выводить «поясняющих» комментариев типа введите число или ответ равен); решения можно отправлять сколько угодно раз (пожалуйста, только без абьюза системы). Для вашего удобства тесты, на которых будут тестироваться ваши решения, являются открытыми. В каждой задаче можно скачать архив тестов (смотрите сайдбар справа, раздел «Материалы соревнования»).
### Перейдём к задаче.
Напишите программу, которая выводит сумму двух целых чисел.
Так как это ознакомительная задача, то вы можете посмотреть и отправить авторские примеры решений (смотрите ссылку в сайдбаре в разделе «Материалы соревнования»). Конечно, в других задачах примеры решений не предоставляются.
### Входные данные
В первой строке входных данных содержится целое число t (1≤t≤104) — количество наборов входных данных в тесте. Далее следуют описания t наборов входных данных, один набор в строке. В первой (и единственной) строке набора записаны два целых числа a и b (−1000≤a,b≤1000).
### Выходные данные
Для каждого набора входных данных выведите сумму двух заданных чисел, то есть a+b.

## G. Возможные друзья (20 баллов)
Во многих социальных сетях у пользователей есть возможность указать других пользователей как своих друзей. Помимо этого, часто существует система рекомендации друзей, которая показывает пользователям людей, с которыми они знакомы косвенно (через кого-то из своих друзей), и предлагает добавить этих людей в список друзей. Вам предстоит разработать систему рекомендации друзей.
В интересующей нас социальной сети n пользователей, каждому из которых присвоен уникальный id от 1 до n. У каждого пользователя этой сети не более 5 друзей. Очевидно, ни один пользователь не является другом самому себе, и если пользователь x в списке друзей у пользователя y, то и пользователь y входит в список друзей пользователя x. Опишем, как должен формироваться список возможных друзей для каждого пользователя. Для пользователя x в список должны входить такие пользователи y, что:
* y не является другом x и не совпадает с x;
* у пользователя y и у пользователя x есть хотя бы один общий друг;
* не существует такого пользователя y′, который удовлетворяет первым двум ограничениям, и у которого строго больше общих друзей с x, чем у y с x.
Иными словами, в список возможных друзей пользователя x входят все такие пользователи, не являющиеся его друзьями, для которых количество общих друзей с x максимально. Обратите внимание, что список возможных друзей может быть пустым.
Вы должны написать программу, которая по заданной структуре социальной сети формирует списки возможных друзей для всех пользователей сети.
Неполные решения этой задачи (например, недостаточно эффективные) могут быть оценены частичным баллом.
### Входные данные
В первой строке заданы два целых числа n и m (2≤n≤50000; 0≤m≤min(n(n−1)2,5n2)) — количество пользователей и количество пар друзей, соответственно. Далее следуют m строк, в каждой из которых заданы два целых числа xi и yi (1≤xi,yi≤n; xi≠yi) — очередная пара друзей в социальной сети. Каждая пара друзей задается не более одного раза; у каждого пользователя не более 5 друзей.
### Выходные данные
Для каждого пользователя от 1 до n выведите в отдельной строке список его возможных друзей в следующем формате: если список возможных друзей пуст, выведите одно целое число 0; иначе выведите id возможных друзей пользователя в возрастающем порядке.

## K. Пользователи и заказы (SQL, 10 баллов)
Это необычная задача — вам надо написать SQL-запрос. В качестве решения вы должны отослать один запрос к базе данных, который возвращает требуемые данные. При проверке вашего решения используется PostgreSQL 15.1. В качестве входных данных вам предоставляется дамп состояния базы данных. Обратите внимание, что время работы вашего решения на тесте включает восстановление состояния базы данных из дампа, но это время значительно меньше ограничения по времени. Вы можете использовать сервис http://sqlfiddle.com/ как инструмент для запуска запросов. Напишите запрос к базе данных, который возвращает всех пользователей, сделавших хотя бы один заказ. Выведите всех таких пользователей, отсортировав их по имени (при равенстве по id). Схема базы данных содержит две таблицы: users и orders, которые связаны отношением «один ко многим». Изучите входные данные примера, чтобы подробно ознакомиться со схемой базы данных. Диаграмма ниже иллюстрирует схему базы данных.
### Входные данные
Входными данными в этой задаче является дамп базы данных. Вам он может быть полезен для ознакомления с состоянием базы данных для конкретного теста. В качестве решения вы должны отправить один SQL-запрос.
### Выходные данные
Ваш SQL-запрос должен вывести всех пользователей в порядке неубывания их имён (по возрастанию id при равенстве имён). Используйте collation по умолчанию.

## I. Планировщик задач (частичное решение 20 баллов из 30) 
Представьте, вы собрали собственный сервер из n
 разнородных процессоров и теперь решили создать для него простейший планировщик задач.

Ваш сервер состоит из n
 процессоров. Но так как процессоры разные, то и достигают они одинаковой скорости работы при разном энергопотреблении. А именно, i
-й процессор в нагрузке тратит ai
 энергии за одну секунду.

Вашему серверу в качестве тестовой нагрузки придет m
 задач. Про каждую задачу вам известны два значения: tj
 и lj
 — момент времени, когда задача j
 придет и время выполнения задачи в секундах.

Для начала вы решили реализовать простейший планировщик, ведущий себя следующим образом: в момент tj
 прихода задачи, вы выбираете свободный процессор с минимальным энергопотреблением и выполняете данную задачу на выбранном процессоре все заданное время. Если к моменту прихода задачи свободных процессоров нет, то вы просто отбрасываете задачу.

Процессор, на котором запущена задача j
 будет занят ровно lj
 секунд, то есть освободится ровно в момент tj+lj
 и в этот же момент уже может быть назначен для выполнения какой-то другой задачи.

Определите суммарное энергопотребление вашего сервера при обработке m
 заданных задач (будем считать, что процессоры в простое не потребляют энергию).

Неполные решения этой задачи (например, недостаточно эффективные) могут быть оценены частичным баллом.

### Входные данные
В первой строке заданы два целых числа n
 и m
 (1≤n,m≤3⋅105
) — количество процессоров и задач соответственно.

Во второй строке заданы n
 целых чисел a1,a2,…,an
 (1≤ai≤106
) — энергопотребление соответствующих процессоров под нагрузкой в секунду. Все энергопотребления различны.

В следующих m
 строках заданы описания задач: по одному в строке. В j
-й строке заданы два целых числа tj
 и lj
 (1≤tj≤109
; 1≤lj≤106
) — момент прихода j
-й задачи и время ее выполнения.

Все времена прихода tj
 различны, и задачи заданы в порядке времени прихода.

### Выходные данные
Выведите единственное число — суммарное энергопотребление сервера, если потреблением энергии в простое можно пренебречь.

## J. Рифмы (частичное решение 15 баллов из 30)

Вы разрабатываете программу автоматической генерации стихотворений. Один из модулей этой программы должен подбирать рифмы к словам из некоторого словаря.

Словарь содержит n
 различных слов. Словами будем называть последовательности из 1
—10
 строчных букв латинского алфавита.

Зарифмованность двух слов — это длина их наибольшего общего суффикса (суффиксом будем называть какое-то количество букв в конце слова). Например:

task и flask имеют зарифмованность 3
 (наибольший общий суффикс — ask);
decide и code имеют зарифмованность 2
 (наибольший общий суффикс — de);
id и void имеют зарифмованность 2
 (наибольший общий суффикс — id);
code и forces имеют зарифмованность 0
.
Ваша программа должна обработать q
 запросов следующего вида: дано слово ti
 (возможно, принадлежащее словарю), необходимо найти слово из словаря, которое не совпадает с ti
 и имеет максимальную зарифмованность с ti
 среди всех слов словаря, не совпадающих с ti
. Если подходящих слов несколько — выведите любое из них.

Неполные решения этой задачи (например, недостаточно эффективные) могут быть оценены частичным баллом.

### Входные данные
Первая строка содержит одно целое число n
 (2≤n≤50000
) — размер словаря.

Далее следуют n
 строк, i
-я строка содержит одну строку si
 (1≤|si|≤10
) — i
-е слово из словаря. В словаре все слова различны.

Следующая строка содержит одно целое число q
 (1≤q≤50000
) — количество запросов.

Далее следуют q
 строк, i
-я строка содержит одну строку ti
 (1≤|ti|≤10
) — i
-й запрос.

Каждая строка si
 и каждая строка ti
 состоит только из строчных букв латинского алфавита.

### Выходные данные
Для каждого запроса выведите одну строку — слово из словаря, которое не совпадает с заданным в запросе и имеет с ним максимальную зарифмованность (если таких несколько — выведите любое).
