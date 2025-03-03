## Рашидова С.В. К-ИСП-39-1 
     
1. Сначала выполняется переход в режим суперпользователя с использованием команды su. Затем открывается файл конфигурации sudoers с помощью редактора visudo для редактирования прав доступа пользователей к команде sudo
<img width="182" alt="image" src="https://github.com/user-attachments/assets/06f403e9-b872-49b3-be8f-32b8da68c5aa" />

2. Начинаем работу с установки утиилиты wget с помощью команды:
sudo yum install wget
![image](https://github.com/user-attachments/assets/629b90b1-48c4-4299-b07a-823bc06a64e0)

3. Вышла ошибка: 'is not a sudoers file'
![image](https://github.com/user-attachments/assets/650e50e9-db9b-4a3d-b901-808454068497)

4. Полученную ошибку 'is not a sudoers file' исправляем через конфигурационный файл:
![image](https://github.com/user-attachments/assets/5007a8e0-e5b3-42ef-90de-fb7d2fc0da61)
![image](https://github.com/user-attachments/assets/76c9d121-a624-4234-838b-692f8216eab3)

5. На скрине устанавливается Docker на CentOS. Использовалась команда `wget` для скачивания репозитория Docker CE:
sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo
В терминале видно, как идет процесс скачивания: распознавание доменного имени, установка соединения, получение HTTP-ответа и сохранение файла `docker-ce.repo.2` в `/etc/yum.repos.d/`. Все прошло успешно, файл скачан! Теперь можно продолжать установку Docker.
![image](https://github.com/user-attachments/assets/dde00933-ba16-4811-a143-cbf739cca7b5)

6.Установка Docker. Вывод из терминала показывает, что происходит установка и проверка пакетов, связанных с Docker через команду sudo yum install docker-ce docker-ce-cli containerd.io
![image](https://github.com/user-attachments/assets/19513d82-733c-4f44-921f-c81dabbc11a3)
![image](https://github.com/user-attachments/assets/dd46d5f2-21ce-40d8-a136-bb7c899a0cc8)

7. Выполнение команды для управления сервисом Docker:
- Команда: 
sudo systemctl enable docker --now
- Что делает: Включает сервис Docker и запускает его сразу же. 
- Вывод: Создается символическая ссылка, которая позволяет Docker запускаться автоматически при загрузке системы.
![image](https://github.com/user-attachments/assets/54dc0152-4217-4961-a448-211bd6dffad1)

8. Установка пакета `curl`:
![image](https://github.com/user-attachments/assets/5c6f95d8-d07a-492b-859e-06355d07d299)

9. Получение последней версии Docker Compose из API GitHub и сохранение её в переменную через команду 'COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)' 
![image](https://github.com/user-attachments/assets/52ab2d93-57a0-42ab-8bb9-f0e08e609166)

10. Скачивание и установка Docker Compose через команду 'sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compos'
![image](https://github.com/user-attachments/assets/bceba0c8-a8c6-4d5d-82b3-7213db6bb0bc)

11. Установлен исполняемый флаг для файла docker-compose в директории /usr/bin
![image](https://github.com/user-attachments/assets/1380838f-fd19-47f5-a03d-423cec354d94)

12. Проверена версия Docker Compose, установлена версия v2.33.1
![image](https://github.com/user-attachments/assets/c33a681d-7bca-4935-bbaf-276537cba977)

13. Клонирован репозиторий grafana_stack_for_docker с GitHub
![image](https://github.com/user-attachments/assets/b1063963-51fc-4e97-9c0a-238fb420a2e4)

14. Перейден в директорию grafana_stack_for_docker
![image](https://github.com/user-attachments/assets/fe1d8a35-3df0-49d8-9899-66c23978492b)

15. Созданы необходимые директории для хранения конфигурации и данных Grafana и Prometheus
![image](https://github.com/user-attachments/assets/e7cae3fc-3c34-4d3a-a14e-a8579dc441e2)

16. Повторно созданы те же необходимые директории для хранения конфигурации и данных
![image](https://github.com/user-attachments/assets/65b871be-c268-4dfc-af19-0a83f03e63f8)

17. Изменены права доступа на указанные директории, назначив владельца текущему пользователю
![image](https://github.com/user-attachments/assets/afa2d8da-3751-44e4-97af-8906e6b981f2)

18. Создан пустой файл grafana.ini в директории конфигурации Grafana
![image](https://github.com/user-attachments/assets/c27a4892-6114-44db-ab5d-cf21fcede1e8)

19. Скопированы конфигурационные файлы в соответствующую директорию
![image](https://github.com/user-attachments/assets/16a7e4bc-5fe6-4be4-b21b-f9f02fb7a664)

20. Переименован файл grafana.yaml в docker-compose.yaml
![image](https://github.com/user-attachments/assets/c86b4351-5410-4ef1-8533-82cd8e8d5251)

21. Запуск сервисов, определенных в docker-compose.yaml в фоновом режиме
![image](https://github.com/user-attachments/assets/26192c78-e045-476d-a4ef-197e3c0cc23d)
![image](https://github.com/user-attachments/assets/3134b193-37b9-40b0-9624-58b5daedc604)
![image](https://github.com/user-attachments/assets/749b4785-3d48-47bd-a203-097113b7c2ef)

22. Открытие файла docker-compose.yaml в редакторе vi с правами суперпользователя
![image](https://github.com/user-attachments/assets/51ddf451-7162-47b5-b81f-9b0af0c5f695)











