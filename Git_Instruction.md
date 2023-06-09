![Logo](Git-Logo-1788C.png)
# Работа с Git и GitHub

## 1. Проверка наличия установленного Git
В терминател выполнить команду `git --version`. Если Git установлен, появится сообщение с информацией о версии программы, иначе будет сообщение об ошибке.

## 2. Установка Git
Загружаем последнюю версию Git с сайта https://git-scm.com/downloads
Устанавливаем с настройками по умолчанию.

## 3. Настройка Git
При первом использовании Git необходимо представиться. Для этого нужно выполнить в терминале две команды:
```
git config --global user.name «Ваше имя английскими буквами»
git config --global user.email ваша почта@example.com
```

## 4. Установка Visual Studio Code
Загружаем последнюю версию Visual Studio Code с сайта https://code.visualstudio.com/Download
Устанавливаем с настройками по умолчанию.

## 5. Запуск терминала
Существует несколько способов для запуска терминала из Visual Studio Code:
1. Вид -> Терминал (View -> Terminal)
2. Горячие клавиши: CTRL+`
3. Терминал -> Создать терминал (Terminal -> New Terminal)

## 6. Открытие папки-репозитория
Существует несколько способов открытия папки, которая будет репозиторием из Visual Studio Code:
1. В проводнике нажать "Открыть папку"
2. Файл - Открыть папку (File - Open Folder)
Выбираем предварительно созданную папку в открывшемся окне

## 7. Проверка статуса Git-репозитория
Для проверки является ли папка Git-репозиторием вводим команду `git status`
Если да, то идем дальше, если нет - получаем ошибку: *fatal: not a git repository (or any of the parent directories): .git*

## 8. Создаем (инициализируем) репозиторий Git
Для инициализации репозитория используем в терминале команду `git init`
После выполнения команды видим сообщение: *Initialized empty Git repository in [адрес локальной папки]*
Вся информация по репозиторию будет содержаться в папке **/.git**. Это скрытая папка

## 9. Создаем в файл
Для отслеживания необходимо иметь что отслеживать. Требуется создать файл.
Создать файл можно несколькими способами:
1. В проводнике Visual Studio Code нажать правой кнопкой и выбрать из контекстного меню "Создать файл" (New File)
2. Файл -> Создать файл (File -> New File)
3. Кнопка "Создать файл в проводнике у наименования папки репозитория
4. Сочетание клавиш CTRL+O
Нажимаем Создать файл и появляется окно, где нужно указать название создаваемого файла, обязательно указывать его с расширением.

## 10. Проверяем статус
После создания файла необходимо проверить статус в терминале командой `git status`

В ответ мы получим сообщение, что находимся в директории **master**, в которой имеется не отслеживаемый файл. Этот файл будет подсвечен красным цветов.
Предлагает выполнить некоторые команды


## 11. Добавляем файл к отслеживанию
Чтобы добавить файл в отслеживание и / или подготовить его к фиксации необходимо воспользоваться командой `git add` и указываем название файла.

Что бы полностью не писать название файла, можно начать писать его начало и использовать клавишу **TAB**, произойдет автозаполнение имени файла.

После выполнения команды `git add` можно вернуться к пункту 10 и проверить статус

## 12. Фиксация изменений в репозитории
Фиксируем изменения в репозитории командой `git commit -m "комментарий"`.

Параметр `-m` дает возможность сразу написать комментарий к фиксации

## 13. Сохранение изменений в файле
Перед подготовкой и фиксацией файла его необходимо сохранить сочетанием клавиш CTRL+S.

Или настроить автосохранение: Файл -> Автосохранение (File -> Auto Save), поставить галочку.

## 14. Разница текущей и зафиксированной версией
Для отображения всех изменений, которые были совершены в текущей версии до фиксации можно воспользоваться командой `gif diff`. Эта команда покажет разницу между текущей версией и последней зафиксированной.

## 15. Комбинированные команды
В Git существует возможность комбинировать команды, например подготовить к фиксации и зафиксировать изменения одной командой `git commit -a`.

Эта команда не может добавлять в отслеживание файл, она только готовит его к фиксации. К тому же, эта команда готовит и фиксирует в commit сразу все файлы в репозитории. Если надо отдельные файлы подготовить и зафиксировать, то следует использовать другие команды

Обязательно к команде `git commit -a` добавлять параметр `-m`, что бы команда выглядела `git commit -a -m <"ваш комментарий">`

## 16. Просмотр истории изменений
Для просмотра истории изменений следует воспользоваться командой `git log`.

Эта команда выводит историю изменений в хронологическом порядке.

> commit 70447a2ee1dde63c66ceaefc43601e42aea30ce6 (HEAD -> master)
>
> Author: Fedor Romanov <flauto86@gmail.com>
>
> Date:   Mon Apr 24 14:43:43 2023 +0300
>
>    Добавили раздел 15. Комбинированные команды


* commit с уникальным хэш-кодом фиксации (неизменяемый идентификатор)
* автор фиксации
* дата и время фиксации (добавления коммита)
* комментарий

Есть возможность запросить сокращенный вариант командой `git log --oneline`. Эта команда выведет сокращенный отчет, где будет только 7 символов хэш-кода и комментарий + указатель того, где мы находимся сейчас.

Если изменений много, и они не помещаются в окно терминала, то внизу будет двоеточие. Следует стрелокой **ВНИЗ** прокрутить до конца, появаится слово *END* и нажать клавишу **Q** для выхода в командный режим терминала.

## 17. `Git commit` без параметра `-m`
В случае, если Вы не указали параметр `-m` для команд `git commit` или `git commit -a`, то следуйте следующей инструкции:
1. Вы перешли во встроенный редактор
2. Нажимаем клавишу **I** - insert (англ. вставка). Увидим в нижней строке ВСТАВКА (INSERT)
3. Пишем комментарий к коммиту
4. Нажимаем **ESC**, что переводит нас в командный режим
5. Набираем команду `:wq` и нажимаем **ENTER** (записать и выйти)

## 18. Подготовка к фиксации всех изменений
Если вы хотите подготовиться к изменениям все файлы в репозитории, то можно воспользоваться командой `git add .`
Эта команда подготовит все изменения во всех файлах репозитория к фиксации.

## 19. Перемещение между сохранениями
Для перемещения между сохранениями (версиями) нужно выбрать необходимую точку сохранения, к которой вы хотите вернуться с помощью команды `git log` или `git log --oneline`.

Далее необходимо выполнить перемещение с помощью команды `git checkout <хеш-код нужного коммита>`, достаточно 4-х символов хеш-кода.

После выполнения этой команды мы возвращаемся к нужно версии и сам файл изменился, он вернулся к этой версии.

Просмотреть историю перемещения метки HEAD можно с помощью команды `git reflog`

Создать новую ветку можно с помощью команды `git switch -c`, вернуться на исходную позицию - `git switch -`

Команда `git switch -` перемещает нас на предыдущую активную ветку

## 20. Игнорирование файлов
Для того, чтобы исключить из отслеживания в репозитории определённые файлы или папки необходимо создать там файл ***.gitignore*** и записать в него их названия или шаблоны, соответствующие таким файлам или папкам.

## 21. Создание веток в Git
По умолчанию имя основной ветки в Git - **master**.

Создать ветку можно командой:
```
git branch <имя новой ветки>
```
А создать ветку с переходом в эту ветку можно командами `git checkout – b <имя новой ветки>` или `git switch -c <имя новой ветки>`

Список веток в репозитории можно посмотреть с помощью команды:
```
git branch
```
Текущая ветка будет отмечена звездочкой: **\*master**

## 22. Перемещение между ветками
Для перемещения между ветками следует использовать команду `git checkout <имя ветки>`. В команде указываем название ветки, куда желаем переместиться.

Возможность одновременного создания ветки и перемещения в нее описана в разделе 21. Создание веток в Git

## 23. Слияние веток
Для слияния веток используется команда `git merge <имя ветки>`.

**Обратите внимание:** вы должны находиться в ветке, с которой необходимо произвести слияние, а в параметре команды следует указать ветку, которую надо с ней слить.
Соответственно, нужно будет воспользоваться командами (при необходимости):
1. `git branch` - определим в какой ветке находимся сейчас
2. `git checkout <имя ветки>` для перемещения в ветку с которой будет происходить слияние или `git switch <имя ветки>`

После слияния веток нужно проверить состояние командой `git log --graph`. Эта команда с параметром `--graph` графически отобразить ветки с коммитами. Можно использовать сокращенный вариант `git log --graph --oneline`

## 24. Разрешение конфликтов
При слиянии веток возможно возникновение конфликтов. Это может произойти, если на одной и той же строке в разных ветках находится разная информация, символы.
В случае конфликта **Visual Studio Code** сигнализирует об этом специальным диалоговым окном в поле окна кода, где будет предложено 4 варианта разрешения конфликта.

После расрешения конфликта обязательно следует сделать коммит слияния!

## 25. Удаление веток
При необходимости мы имеем возможность удалить ненужные ветки. Сделать это можно с помощью команды
```
git branch -d <имя ветки>
```
<имя ветки> - это ветка, которую нужно удалить.

Убедитесь, что во время ввода команды вы не находитесь в ветке, которую пытаетесь удалить. В случае необходимости переместитесь в другую ветку.

Обычно мы удаляем уже слитую ветку, но в некоторых случаях может потребоваться удаление неслитой ветки. Сделать это можно командой 
```
git branch -D <имя ветки>
```
Большая буква **D** означает принудительность действия.

## 26. Работа с удалёнными репозиториями GitHub

1. Создать аккаунт на GitHub
2. Создать локальный репозиторий
3. Создать удаленный репозиторий
Перейти на сайт GitHub и выбрать справа наверху у знака + под стрелкой "New repository"
Далее необходимо придумать имя репозитория: Reporitory name
Ниже можно написать описание ревозитоия, но это не обязательно (Description (optional))
Определить доступ к репозиторию
Public - публичный
Private - приватный
Можно сразу создать и добавить файл README, .gitignore (есть варианты шаблонов) и файл License
Нажимаем Create repository

4. Связать локальный репозиторий с удаленным
После создания репозитория предлагается 3 действия, но мы вибираем второй вариант для уже существующего локального репозитория.
Нужно выполнить 3 команды, которые предлагаеи GitHub
`git remote add origin https://github.com/Flauto86/Git_study.git` - эта команда связывает локальный репозиторий с удаленным
`origin` - это название удаленного репозитория в локальном, что б не указывать каждый раз полный путь

Проверить, привязан ли локальный репозиторий к удаленному можно командой `git remote`
Если привязан, то команда вернет `origin` - название удаленного репозитория
а команда `git remote -v` покажет дополнительную информацию - адреса для получения и отправки изменений

`git branch -M main` - эта команда переименовывает название локальной ветки в main (master -> main)

`git push -u origin main` - отправляет локальные изменения в удаленный репозиторий
Если в программе эта команда делается впервые, то будет предложено авторизоваться на вашем аккаунте на GitHub, а потом все изменения будут отправлины в GitHub
Переходим в удаленный репозиторий и обновляем страницу. Вся информация должна появиться на странице вашего репозитория.

Добавить удаленный репозиторий к проекту:
```
git remote add <имя для репозитория> <url-адрес репозитория в сети>
```
Проверяем статус `git status`

Сохраняем изменения в локальном репозитории `git add <имя файла>` и `git commit -m <сообщение>`, после этого отправляем изменения в удаленный репозитория `git push`

Для получения и слияния изменений из удаленного репозитория используется команда `git pull`.

Отправить изменения локального репозитория в удаленный `git push`
