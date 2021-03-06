# __*Инструкция по работе с системой контроля версий Git*__

![Логотип Git](git.png)

Git — самая популярная в мире распределённая система контроля версий. Линус Торвальдс, разработчик ядра ОС Linux, создал этот инструмент ещё в 2005 году, а сегодня Git активно поддерживается как проект с открытым исходным кодом. Огромное количество открытых и коммерческих проектов используют Git для контроля версий.

## __*Задаем имя пользователя и электронный адрес*__

Имя пользователя нужно, чтобы привязывать коммиты к вашему имени. Задать или изменить имя пользователя можно с помощью команды:

   git config

Новое имя будет автоматически отображаться в последующих коммитах, отправленных на GitHub через командную строку. Если хотите скрыть своё реальное имя, можно использовать в качестве имени пользователя Git произвольный набор символов. Полная команда выглядит вот так:

    git config --global user.name "Ivan Ivanov"

Кроме того, командой git config можно изменять адрес электронной почты, привязанный к вашим коммитам Git. Новый адрес электронной почты будет автоматически отображаться во всех дальнейших коммитах, поданных на GitHub через командную строку.

    git config --global user.email "ivan.ivanov@list.ru"   

## __*Инициализация репозитория*__

Чтобы инициализировать новый репозиторий, нужно ввести в терминале 

    git init

При инициализации будет создана скрытая папка. В ней содержатся все объекты и ссылки, которые Git использует и создаёт в истории работы над проектом.

## __*Проверка состояния репозитория*__

Для проверки состояния репозитория нужно спользовать команду

    git status

Данная команда сообщит, нужно ли что-то коммитить.

## __*Сохранение изменений*__

Сохранение изменений в большинстве случаев производится в два этапа:

**1**. Предварительно сохранив изменения в файле, переходим в терминал и используем команду 

    git add

Данная команда добавляет файл индекс

**2**. И выполняем сохраение при помощи команды

    git commit

При создании коммита в репозитории можно добавить однострочное сообщение с помощью параметра commit с флагом __-m__. Само сообщение вводится непосредственно после флага, в __кавычках__:

   git commit -m "init commit" 

__ВАЖНО!__ При сохранении необходимо писать понятные комментарии, с которыми вы с легкостью разберетесь в будущем и благодаря этому без труда переключитесь на нужный коммит!

## __*История изменений*__

Историю изменений можно просмотреть с помощью команды

    git log

Данная команда перечисляем все коммиты __*в обратном порядке*__. Если добавить к команде __--oneline__, то вы сможете просмотреть свои коммиты в более удобном - *компактном* виде.

## __*Переключение между сохранениями*__

Для переключения между сохранениями используем команду 

    git checkout

После комманды нужно ввести номер коммита, на который собираетесь переключиться.

## __*Сравнение версий*__

Можно просматривать список изменений, внесённых в репозиторий, используя:

    git diff

Команда __git diff__ выводит все неподтвержденные изменения, внесенные после последнего коммита. Для просмотра подготовленных изменений необходимо добавить флаг:

    git diff --staged

## __*Создание новой ветки*__

Создать новую ветку можно с помощью параметра __branch__, указав имя ветки:

    git branch branch_name

## __*Переход на другую ветку*__

    git checkout branch_name

## __*Просмотр списка веток*__

Можно просматривать полный список веток, используя параметр branch. Команда отобразит все ветки, отметит текущую *звёздочкой* (*) и выделит её цветом.

    git branch

Также можно вывести список удалённых веток с помощью флага -a:

    git branch -a

## __*Удаление ветки*__

Удалить ветку можно параметром branch с добавлением флага __-d__ и указанием имени ветки. Если вы завершили работу над веткой и объединили её с основной, можно её удалить без потери истории. Однако, если выполнить команду удаления до слияния — в результате появится сообщение об ошибке. Этот защитный механизм предотвращает потерю доступа к файлам.

    git branch -d branch_name

## __*Слияние двух веток*__

Объединить две ветки можно параметром __merge__ с указанием имени ветки. Команда объединит указанную ветку с основной:

    git merge branch_name

Данную команду необходимо вводить, находясь в ветке, в которую необходимо _залить_ изменения.

## __*Выводим список коммитов в виде красивого графа/дерева*__

    git log --graph

## __*Прекращение слияния веток при конфликте*__

Прервать слияние в случае конфликта можно параметром merge с флагом __--abort__. Он позволяет остановить процесс слияния и вернуть состояние, с которого этот процесс был начат.

    git merge --abort

Также при конфликте слияния можно использовать параметр reset, чтобы восстановить конфликтующие файлы до стабильного состояния.

    git reset

# Ссылки

Для детального ознакомления с командами __git__ воспользуйтесь [ссылкой](https://docs.microsoft.com/ru-ru/azure/devops/repos/git/command-prompt?view=azure-devops "Справочник по командам Git")