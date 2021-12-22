# Лабораторная работа №2
> Цель работы: Поиск и устранение SQL Injection.
> ## Задание 1

1. Список книг и авторов
![image](https://user-images.githubusercontent.com/82168526/146243993-f962c682-3052-40cb-8008-0940bb3df3c9.png)

8. Обнаружение SQL инъекции
При вводе ') в фильтр выводится сообщение об ошибке и запрос к базе данных
![image](https://user-images.githubusercontent.com/90596797/147047474-c9e866cd-32ca-4150-8a11-fb6d0f499963.png)



9.1. Обход установленного фильтра
![image](https://user-images.githubusercontent.com/82168526/146244120-fa631d05-9899-48c1-9cdd-2422fd31aab0.png)


9.2. Получение данных из таблицы users
![image](https://user-images.githubusercontent.com/82168526/146244144-31241a8a-2a14-4488-b617-2621262b4286.png)

9.3. Похищение пароля пользователя
![image](https://user-images.githubusercontent.com/82168526/146244157-80ed99d1-130e-4a12-8a08-a90eb4130b5b.png)

10. Исправление уязвимости
![image](https://user-images.githubusercontent.com/90596797/147051589-25bc193c-6332-41e6-8386-dfd151f4bc3f.png)


10.1 Исправление уязвимости с помощью параметризации запроса:

![image](https://user-images.githubusercontent.com/90596797/147051742-768fe71d-49ee-46d4-bd55-36129f2c9eaf.png)

