# devops_k8s
Работу выполнили Золотарев Данил и Ракитин Арсений из группы ИТХ-2-2021.
##
1. Minicube был уже установлен, запускаем его.
   
   ![image](https://github.com/user-attachments/assets/43337062-ffeb-494c-8568-cd269e26e2c8)
   
2. Проверяем, какие у нас есть ноды и сервисов в кластере.

   ![image](https://github.com/user-attachments/assets/9398d327-57dc-4d5c-9d22-f2d6963619e9)

3. Производим сборку образа из исходников прямо внутри minikube с помощью команды "minikube image build -t flask:v1 flask_redis/" 
4. Загружаем готовый образ redis внутрь кластера с помощью команды "minikube image load redis:alpine"
5. Проверяем, что образы стали доступны внутри кластера
   
   ![image](https://github.com/user-attachments/assets/dda72c10-b916-44d6-85fb-d94db06b3025)

6. Создаём манифесты для каждого сервиса.

   ![image](https://github.com/user-attachments/assets/d4f3566c-80b3-4514-a797-1c6af657d468)

7. Применяем каталог манифестов целиком.

   ![image](https://github.com/user-attachments/assets/022f1cbc-3da5-4892-849e-6fe2f50df384)
   
8. Открываем порт 8000 и пробрасываем трафик внутрь машины с помощью команды "minikube tunnel --bind-address 10.0.2.15".
9. Проверяем http://192.168.0.11:8000. Как видно, мы подключились и попадаем на разные поды при подключениях.

    ![image](https://github.com/user-attachments/assets/44d3d26e-5583-480c-8f46-edca2d425a19)

10. Обновим наше приложение. (добавим version 5 в текст).

    ![image](https://github.com/user-attachments/assets/1673e8ae-8f73-4e6f-92bb-86c060ace324)

11. Пересобираем образ с новым тегом :v5 и делаем новый образ доступным в кластере minikube.

    ![image](https://github.com/user-attachments/assets/3f659a10-4a88-4f80-9e2b-84a9e43d2fb1)

12. Обновляем поды на новую версию – патчим деплоймент.
    
    ![image](https://github.com/user-attachments/assets/6ad28368-d7d1-40d3-a529-db48d62ff323)

13. Поды обновились, задача выполнена.
    ![image](https://github.com/user-attachments/assets/956b89be-fb85-484f-97f5-57fe4f52e464)



