-       1. Какого типа команда cd? Попробуйте объяснить, почему она именно такого типа; опишите ход своих мыслей,
-       если считаете что она могла бы быть другого типа.
-
-       Ответ:
-       Это команда встроенная
-       cd является встроенной оболочкой, и ее поведение может немного отличаться от оболочки к оболочке. Он использует переменные среды оболочки для 
-       определен-ия необходимой информации для его выполнения.
-       Теоретически можно сделать CD внешней программой, но после смены деректории необходимо вызвать bash из 
-       этого (нового каталога), но тогда мы получим новый shell.
-       И выходя из сесии придется выходить, опять же, из всех сессий, которые создали при каждом вызове внешней CD.
______________________________________________________________________________________________________________________
-       2. Какая альтернатива без pipe команде grep <some_string> <some_file> | wc -l? man grep поможет в ответе 
-       на этот вопрос. Ознакомьтесь с документом о других подобных некорректных вариантах использования pipe.
-
-       Ответ:
-
-	➜  ~ cat one_bash 
-	if [[ -d /tmp ]]
-	dfghjkl
-	ghjkl;'lkjh
-	9988
-	➜  ~ grep 9988 one_bash -c    
-	1
-	➜  ~ grep 9988 one_bash |wc -l
-	1 
________________________________________________________________________________________________________________________
-	3. Какой процесс с PID 1 является родителем для всех процессов в вашей виртуальной машине Ubuntu 20.04?
-	
-	Ответ:
-	На виртуальной машине  - systemd:
-	➜  ~ pstree -p
-	systemd(1)─┬─ModemManager(895)─┬─{ModemManager}(916)
-           │                   └─{ModemManager}(921)
-	
_______________________________________________________________________________________________________________________
-	4. Как будет выглядеть команда, которая перенаправит вывод stderr ls на другую сессию терминала?
-	
-	Ответ:
-	ls -l \root 2>/dev/pts/1
-	Вывод в другой сессии pts/1:
-	who
-	pi       pts/0        2022-06-13 06:01 (192.168.1.51) 
-	pi       pts/1        2022-06-13 06:01 (192.168.1.51)
-	➜  ~ ls: cannot access 'root': No such file or directory
________________________________________________________________________________________________________________________
-	5. Получится ли одновременно передать команде файл на stdin и вывести ее stdout в другой файл? Приведите работающий пример.
-	Ответ:
-	cat one_bash	
- 	if [[ -d /tmp ]]
-	dfghjkl
-	ghjkl;'lkjh
-	9988
-	cisco_55777
-	cat one_bash_out
- 	cat: one_bash_out: No such file or directory
-	cat <one_bash >one_bash_out
-	cat one_bash_out 
-       cat one_bash
-       if [[ -d /tmp ]]
-       dfghjkl
-       ghjkl;'lkjh
-       9988
-       cisco_55777
_______________________________________________________________________________________________________________________________
-	6. Получится ли вывести находясь в графическом режиме данные из PTY в какой-либо из эмуляторов TTY? Сможете ли вы наблюдать выводимые данные?
-	
-	Ответ:
-	tty
-	dev/pts/3
-	echo Hi friends from pts3 to tty3 >/dev/tty3
-		
➜  ~ 	
