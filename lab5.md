## Лабораторная работа No5

## Задание №1
Будем работать в Git Bash
1) Создадим репозиторий `lab_5.linux` и клонируем его с помощью команды
   ```
   git clone https://github.com/haha523/lab_5.linux.git
   ```
   ![image](https://github.com/haha523/lab_5.linux/blob/b379dd2e261f27ee33281934ff030ae6a70689dc/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20git_clone.png)

2) Перейдем в папку репозитория:
   ```
   cd lab_5.linux
   ```
   ![image](https://github.com/haha523/lab_5.linux/blob/512657df8c8f375109c4b55ea5b50a6b47c67037/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20cd.png)
3) Проверим наличие папки .git/hooks/ командой:
   ```
   ls -la .git/hooks/
   ```
   ![image](https://github.com/haha523/lab_5.linux/blob/512657df8c8f375109c4b55ea5b50a6b47c67037/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20ls%20-la%20.png)

4) Перейдем в эту папку и создадим файл pre-commit
   ```
   cd .git/hooks/ && nano pre-commit
   ```
   ![image](https://github.com/haha523/lab_5.linux/blob/512657df8c8f375109c4b55ea5b50a6b47c67037/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20nano%20pre-commit.png)

5) Напишем в нем скрипт для проверки файла перед commit
   ![image](https://github.com/haha523/lab_5.linux/blob/512657df8c8f375109c4b55ea5b50a6b47c67037/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20c%E1%BB%A7a%20pre-commit.png)

6)  Сделаем файл исполняемым
     ```
     chmod +x pre-commit
     ```
    ![image](https://github.com/haha523/lab_5.linux/blob/512657df8c8f375109c4b55ea5b50a6b47c67037/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20chmod%20%2Bx%20pre-commit.png)

7) Вернемся в папку репозитория и создадим новый текстовый файл `task_1_1.txt`
   ```
   nano task_1_1.txt
   ```
   ![image](https://github.com/haha523/lab_5.linux/blob/512657df8c8f375109c4b55ea5b50a6b47c67037/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20c%E1%BB%A7a%20nano%20task_11.txt.png)
   Внесем в него какой-то текст. Главное, чтобы в нем присутствовало слово `Автор`:
   ![image](https://github.com/haha523/lab_5.linux/blob/512657df8c8f375109c4b55ea5b50a6b47c67037/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20task_1_1.png)

8) Сохраним файл, попробуем сделать commit и отправить его в репозиторий
   ```
   git add task_1_1.txt
   git commit -m "Добавлен корректный текстовый файл"
   git push origin main
   ```
   ![image](https://github.com/haha523/lab_5.linux/blob/512657df8c8f375109c4b55ea5b50a6b47c67037/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20c%E1%BB%A7a%20git%20add%20task_1_1.txt.png)
   
   После выполнения команды `git commit -m "Добавлен корректный текстовый файл"` видим сообщение о том, что файл прошел проверку, и в нем есть слово "Автор"

9) Зайдем в наш репозиторий и увидим, что файл `task_1_1.txt` успешно добавлен вместе со своим содержимым
   
    ![image](https://github.com/haha523/lab_5.linux/blob/fdef941e7f8f1fddf04cb645cb704b967797b043/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20task_1_1.github.png)
   
    ![image](https://github.com/haha523/lab_5.linux/blob/fdef941e7f8f1fddf04cb645cb704b967797b043/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20task_1_1.github.%20n%E1%BB%99i%20dung.png)

10) Аналогично создадим файл `task_1_2.txt`, в котором не будет слова `Автор` и повторим те же действия, что с предыдущим файлом
    ```
    nano task_1_2.txt
    git add task_1_2.txt
    git commit -m "Попробуем добавить некорректный файл"
    ```
    
    ![image](https://github.com/haha523/lab_5.linux/blob/fdef941e7f8f1fddf04cb645cb704b967797b043/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20c%E1%BB%A7a%20task_1_2.png)
    
    ![image](https://github.com/haha523/lab_5.linux/blob/fdef941e7f8f1fddf04cb645cb704b967797b043/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20nano%20task_1_2.txt.png)

    Получаем сообщение о том, что слова "Автор" нет в файле -> мы не можем сделать commit и  отправить изменения на сайт:
    
    ![image](https://github.com/haha523/lab_5.linux/blob/00e234e0d6c6d9c7020784c13c8c986c75e2b5ab/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20git%20status.png)

    Действительно, выполня все эти действия и перейдя на сайт репозитория, мы не увидим там файл `task_1_2.txt`

11) Чтобы убрать файл из раздела тех, которые будут закоммичены, отменим предыдущее действие, а также проверим состояние рабочего каталога и статус файлов
    ```
    git reset HEAD task_1_2.txt
    git status
    ```
    ![image](https://github.com/haha523/lab_5.linux/blob/00e234e0d6c6d9c7020784c13c8c986c75e2b5ab/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20git%20reset%20HEAD%20task_1_2.txt.png)

## Задание №2
1) Проверим, что Git Flow установлен
   ```
   git flow version
   ```
   ![image](https://github.com/haha523/lab_5.linux/blob/6299f401c10f37b309b1969d4d25606f2ed7052b/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20git%20flow%20version.png)

2) Инициализируем Git Flow и оставим название веток по умолчанию
   ```
   git flow init
   ```
   ![image](https://github.com/haha523/lab_5.linux/blob/6299f401c10f37b309b1969d4d25606f2ed7052b/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20git%20flow%20init.png)

3)  Создадим ветку для нового функционала
     ```
     git flow feature start task-management
     ```
    ![image](https://github.com/haha523/lab_5.linux/blob/6299f401c10f37b309b1969d4d25606f2ed7052b/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20git%20flow%20feature%20start%20task-management.png)

4) Создадим новый Python-файл `task_manager.py` и откроем его
   ```
   nano task_manager.py
   ```
   Напишем в файле такой скрипт:

   ![image](https://github.com/haha523/lab_5.linux/blob/6299f401c10f37b309b1969d4d25606f2ed7052b/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20nano%20task_manager.py.png)

5) Закоммитим это файл с помощью команд
   ```
   git add task_manager.py
   ```
   ![image](https://github.com/haha523/lab_5.linux/blob/6299f401c10f37b309b1969d4d25606f2ed7052b/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20git%20add%20task_manager.py.png)
   ```
   git commit --no-verify -m "Добавлен функционал управления задачами"
   ```
   --no-verify необходимо для того, чтобы отключить проверку файлов из предыдущего задания
   ![image](https://github.com/haha523/lab_5.linux/blob/6299f401c10f37b309b1969d4d25606f2ed7052b/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20git%20commit%20--no-verify%20-m%20.png)

   
6) Предположим, что мы закончили разработку, поэтому удалим ветку и переключимся на ветку develop с помощью команды:
    ```
    git flow feature finish task-management
    ```
    ![image](https://github.com/haha523/lab_5.linux/blob/6299f401c10f37b309b1969d4d25606f2ed7052b/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20git%20flow%20feature%20finish%20task-management.png)

7) Создадим релиз при помощи команд:
    ```
    git flow release start v1.0.0
    ```
     ![image (https://github.com/haha523/lab_5.linux/blob/6299f401c10f37b309b1969d4d25606f2ed7052b/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20c%E1%BB%A7a%20git%20flow%20release%20start%20v1.0.0.png)
    ```                                                                                                                                                                                   
    echo "v1.0.0" > version.txt
    git add version.txt
    git commit -m "Обновлена версия для релиза v1.0.0"
    git flow release finish v1.0.0
    ```

   ![image](https://github.com/haha523/lab_5.linux/blob/6299f401c10f37b309b1969d4d25606f2ed7052b/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20echo%20v1.0.0%20%20version.txt.png)

   ![image](https://github.com/haha523/lab_5.linux/blob/6299f401c10f37b309b1969d4d25606f2ed7052b/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20git%20flow%20release%20finish%20v1.0.0.png)


8) Создадим ветку для срочного исправления ошибки:
    
    ```
    git flow hotfix start hotfix-1.0.1
    ```
    
    ![image](https://github.com/haha523/lab_5.linux/blob/6299f401c10f37b309b1969d4d25606f2ed7052b/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20git%20flow%20hotfix%20start%20hotfix-1.0.1.png)
   
9) Внесем изменения в локальный репозиторий в ветку master:
    
    ```
    git add task_manager.py
    git commit --no-verify-m "Исправлена критическая ошибка"
    git flow hotfix finish hotfix-1.0.1
    ```
    
    ![image](https://github.com/haha523/lab_5.linux/blob/6299f401c10f37b309b1969d4d25606f2ed7052b/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20git%20add%20task_manager.py.png%20v%C3%A0%20git%20commit%20--no-verify%20-m%20git%20commit%20--no-verify%20-m%20%D0%98%D1%81%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B0%20%D0%BA%D1%80%D0%B8%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B0%D1%8F%20%D0%BE%D1%88%D0%B8%D0%B1%D0%BA%D0%B0.png)
    
    ![image](https://github.com/haha523/lab_5.linux/blob/6299f401c10f37b309b1969d4d25606f2ed7052b/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20git%20flow%20hotfix%20finish%20hotfix-1.0.1.png)


10) Отправим изменения в ветку develop
    ```
    git checkout develop
    git push origin develop
    ```
    ![image](https://github.com/haha523/lab_5.linux/blob/6299f401c10f37b309b1969d4d25606f2ed7052b/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20git%20checkout%20develop%20v%C3%A0%20git%20push%20origin%20develop.png)


11) Отправим изменения в ветку main
    ```
    git checkout main
    git push origin main
    ```
    ![image](https://github.com/haha523/lab_5.linux/blob/6299f401c10f37b309b1969d4d25606f2ed7052b/png%20for%20lab5/h%C3%ACnh%20%E1%BA%A3nh%20c%E1%BB%A7a%20git%20checkout%20main%20v%C3%A0%20git%20push%20origin%20main.png)
    
12) Перейдем в наш репозиторий и увидим:

    ![image](https://github.com/haha523/lab_5.linux/blob/a4882f57ff08f838b97961828a74c8161d36eebb/png%20for%20lab5/github%20%20cu%E1%BB%91i%20c%C3%B9ng.png)





