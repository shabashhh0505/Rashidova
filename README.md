<img width="245" alt="image" src="https://github.com/user-attachments/assets/3073744f-f01a-4d9b-98ca-72b1a68d6a82" /># Rashidova
Начинаем работу с установки утиилиты wget с помощью команды:
sudo yum install wget
<img width="305" alt="1" src="https://github.com/user-attachments/assets/b34afb26-a084-4fa2-afd4-fcffc9a125ef" />
Полученную ошибку "is not a sudoers file" исправляем через конфигурационный файл:
<img width="245" alt="2" src="https://github.com/user-attachments/assets/85406f1a-1d87-4768-8823-67427f4cbbcb" />
<img width="314" alt="image" src="https://github.com/user-attachments/assets/b480300d-f39c-460c-87bd-6ce032da66b0" />

На скрине устанавливается Docker на CentOS. Использовалась команда `wget` для скачивания репозитория Docker CE:

shell
bash
sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo

В терминале видно, как идет процесс скачивания: распознавание доменного имени, установка соединения, получение HTTP-ответа и сохранение файла `docker-ce.repo.2` в `/etc/yum.repos.d/`. Все прошло успешно, файл скачан! Теперь можно продолжать установку Docker.
![image](https://github.com/user-attachments/assets/dde00933-ba16-4811-a143-cbf739cca7b5)
