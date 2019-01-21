# Cmd Windows
1. `cd` - перемещение по каталогам как в linux 

2. `del` - удаление файлов (если указать название папки то удалит всё её содержимое) <br>
`del file.txt` - пример 

3. `dir` - вывод содержимого текущего каталога <br>
`dir /d` - вывод в столбец <br>
`dir /b` - вывод только имен файлов <br>

4. `md` - создание папки <br>

5. `rd` - удаление папки <br>
`rd /s` - удаление папки рекурсивно <br>
`rd /s /q` - удаление папки рекурсивно и без вопросов <br>

6. `move` - перемещение папок и файлов <br>
`move file.txt folder/file2.txt` можно переименовывать 

7. `copy` - копирование файлов <br>
если введен каталог то скопирует всё содержимое <br>
`xcopy` - универсальное копирование для файлов и папок 

8. `tskill` - завершение процесса <br>
`tskill program` (без .exe) 

9. `type` - вывод содержимого файлов <br>
`type c:\file.txt` 

10. `echo > file.txt` - запись в файл (старые данные удаляются) <br>
`echo » file.txt` - запись в файл (старые данные не удаляются) 

11. `tree` - древовидное отображение содержимого текущего каталога <br>
`tree /f` - вывод включая файлы 

12. `start` - запуск программы 

13. `help` - список команд (помощь) <br>
команда /? - помощь по команде 

14. `schtasks` - планировщик задач <br>
    /tn - task name<br>
    /tr - task run путь и имя программы которая должна запуститься<br>
    /c - command команда в консоли которая будет выполнена<br>
    /sc - частота повторения<br>
    /st - start time<br>
    /sd - start date
`schtasks /create /tn "run" /tr "cmd /c start c:\users\admin\desktop\speccy" /sc once /st 22:30 /sd 16/05/`

15. `winsat cpu -v` - информация о компьютере (запускать консоль от имени админа)

16. `chkdsk C: /r /f` (проверка диска и восстановление)<br>
      /F                  Исправляет ошибки на диске.<br>
      /R                  Ищет поврежденные сектора и восстанавливает уцелевшую

17. `diskpart>`<br>
    `select disk=1` - выбор диска<br>
    `list disk` - список дисков и информация о них<br>
    `list partition` - список разделов диска<br>
    `create partition primary size=500` - создание primary (основного) раздела с размеров 500 мб<br>
    `format fs=ntfs labe=name quick` - форматирование тома, fs (file system) quick быстрое форматирование label - имя<br>
    `assign letter=F` - присвоение тому буквы<br>
    `convert dynamic` - конвертация диска в динамический,<br>
       другие примеры:<br>
       `convert mbr`<br>
       `convert gpt`<br>
    `extend size=500` - расширение тома на 500 мб (перед операцией выбрать диск и том)<br>
    `shrink desired=200` - уменьшение тома на 200 мб<br>
    `delete (partition,volume,disk)` - удаление тома или диска или раздела (перед опирацией соответственно выбрать)

18. `net help` - справка по net<br>
    a) `net user` - список пользователей<br>
       `net user Dima новый пароль (или * чтобы ввести отдельно)`<br>
       `net user Dima qwerty /ADD /ACTIVE:YES` - добавление активной учетной записи с логином и паролем Dima и qwerty<br>
       `net user Dima /comment:"simple chel" /fullname:"Vergulev Dima"` - изменение данных о пользователе Dima<br>
       `net user Dima /delete` - удаление пользователя Dima<br>
       `net localgroup Администраторы Dima /add` - добавление пользователя Dima в группу Администраторы<br>
       `net localgroup Администраторы Dima /delete` - удаление пользователя Dima из группы Администраторы

19. netsh /?

    `netsh interface show interface` - показывает все подключенные интерфейсы (которые в параметрах адаптера)<br>
    `netsh interface set interface name="Ethernet" newname="Ethernet2"` - переименование интерфейса<br>
    `netsh interface set interface name="Ethernet" admin=disabled` - отключение интерфейса<br>
    `netsh interface set interface name="Ethernet" admin=enabled` - включение интерфейса<br>
    `netsh interface ipv4 show adresses` - показ всех интерфейсов с их ipv4 адрессами<br>
    `netsh interface ipv4 set adress name="Ethernet" source=dhcp` - включение интерфейсy Ethernet'y dhcp - автоматическая адрессация ip<br>
    `netsh interface ipv4 add adress name="Ethernet" adress=192.168.10.150 mask=255.255.255.0`<br>
    `netsh interface ipv4 add adress name="Ethernet" gateway=192.168.134.250 gwmetric=1` - шлюз канала<br>
    `netsh -r 192.168.10.150 -u wsr -p 1234` - удаленное подключение
    `hostname` - имя компьютера
