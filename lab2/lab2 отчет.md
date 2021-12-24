# Лабораторная работа №2
> Цель работы: Поиск и устранение SQL Injection.
> ## Задание 1

1. Список книг и авторов
![image](https://user-images.githubusercontent.com/90596797/147355811-3f02416b-a599-43fd-9baf-864a6fe9a2ef.png)

8. Обнаружение SQL инъекции
При вводе ') в фильтр выводится сообщение об ошибке и запрос к базе данных
![image](https://user-images.githubusercontent.com/90596797/147047474-c9e866cd-32ca-4150-8a11-fb6d0f499963.png)



9.1. Обход установленного фильтра
![image](https://user-images.githubusercontent.com/90596797/147355531-53a1ad19-7010-4bdd-819d-6679bba24461.png)


9.2. Получение данных из таблицы users
![image](https://user-images.githubusercontent.com/90596797/147355607-bcfb4f04-86f3-4f3f-9139-43567a378370.png)

9.3. Похищение пароля пользователя

![image](https://user-images.githubusercontent.com/90596797/147355624-1e387872-97c3-42b1-86dc-a489993644fc.png)

10. Исправление уязвимости
 
![image](https://user-images.githubusercontent.com/90596797/147051589-25bc193c-6332-41e6-8386-dfd151f4bc3f.png)


10.1 Исправление уязвимости с помощью параметризации запроса:
![image](https://user-images.githubusercontent.com/90596797/147355671-ef3f5cb3-3866-4bf0-909d-16ebe59f609f.png)
![image](https://user-images.githubusercontent.com/90596797/147355701-0497ad2f-466f-4c10-ac4c-1ab0ad5f3502.png)

