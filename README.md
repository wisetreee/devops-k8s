# devops_k8s
Работу выполнил Ракитин Арсений, группа ИТХ-2-2021.
#

1. Создаём приложение Flask + Redis, пишем YAML-манифесты для k8s. (kubectl и minicube уже были установлены).
2. Собираем образ из исходников внутри minikube.
   
   ![image](https://github.com/user-attachments/assets/8e22c778-eb7d-43f4-bc0d-0aabf2fb5375)
  
3. Для Redis загружаем образ.

   ![image](https://github.com/user-attachments/assets/525ef6a6-8b51-4bf7-bf68-e7727002945c)

   Можем посмотреть наши образы введя команду minikube image ls:

   ![image](https://github.com/user-attachments/assets/54241171-c9d5-4d34-87ee-a006a95f1be8)

4. На основе манифестов создаём деплоймент.

   ![image](https://github.com/user-attachments/assets/3a234094-ed13-400c-be1b-ef820d15667b)

  Можем посмотреть наши сервисы и поды.

  ![image](https://github.com/user-attachments/assets/cbf826db-582a-4b4c-b128-381dade0e5d7)

5. Пробрасываем порт на виртуальную машину, на которой запущен наш кластер.

   ![image](https://github.com/user-attachments/assets/429920fa-8f43-4260-8a98-85fb968ab01f)

6. В отдельном окне разрешаем проброс трафика vm внутрь minikube.

   ![image](https://github.com/user-attachments/assets/87cf7389-6c28-4ae7-ac71-327dc0bf4e15)

7. Проверяем в браузере IP хоста и порт 8000. Все работает.

   ![image](https://github.com/user-attachments/assets/d3f15472-beab-4449-bdca-0890af1ec1ff)

8. Обновим наше приложение: добавим "VERSION 5" в строку вывода.

   ![image](https://github.com/user-attachments/assets/2d450962-69df-4c7a-a0d8-d6b54e1acecf)

9. Пересобираем образ с тегом v5.

    ![image](https://github.com/user-attachments/assets/96a14a6e-85b1-443b-af06-9ee43122207f)
   
10. После патча деплоймента можем видеть, как поды обновляются на новую версию:

    ![image](https://github.com/user-attachments/assets/7a8f5145-b6dc-45b8-90a4-8038f2ea96f5)

11. Проверим браузер ещё раз. Приложение обновилось, а это значит, что наша задача выполнена!

    ![image](https://github.com/user-attachments/assets/fa932092-79d3-4a2f-bf51-e801d4139d16)







 
