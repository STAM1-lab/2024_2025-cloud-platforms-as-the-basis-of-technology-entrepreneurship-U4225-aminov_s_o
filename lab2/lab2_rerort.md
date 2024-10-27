University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Cloud platforms as the basis of technology entrepreneurship](https://) ADD link
Year: 2024/2025
Group: U4225
Author: Aminov Stanislav Olegovich
Lab: Lab2
Date of create: 27.10.2024
Date of finished: 

**1. Создал Cloud Run с помощью дефолтного сервиса**
![](https://github.com/STAM1-lab/2024_2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-aminov_s_o/blob/main/lab2/lab2_screenshots/img1.jpg)

**2. Протестировал сервис**
![](https://github.com/STAM1-lab/2024_2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-aminov_s_o/blob/main/lab2/lab2_screenshots/img2.jpg)

**3. Проанализировал логи**
Из логов можно получить следующую информацию:
  В 18:51 был создан и успешно запущен сервис hello-saminov в Google Cloud Run. Лог показывает, что контейнер стартовал корректно и начал принимать HTTP-запросы на порту 8080.
  В 19:00 сервису начали поступать запросы через браузер (Chrome) на URL https://hello-saminov-307056602443.us-central1.run.app/
  Запросы выполнялись успешно, и сервис отвечал на них в пределах нескольких миллисекунд.
![](https://github.com/STAM1-lab/2024_2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-aminov_s_o/blob/main/lab2/lab2_screenshots/img3.jpg)

**4. Проанализировал метрики**
*Request count* - количество обработнных запросов 
*Request Latencies* - среднее время задержки (5-10 мс)
*Container Instance Count* - Количество контейнеров:
  active: количество активных контейнеров.
  idle: количество простаивающих контейнеров.
*Billable Container Instance Time* - время, за которое контейнеры были активны и оплачиваемы
*Container CPU Utilization* - Загрузка CPU контейнеров
*Container memory utilization* - Загрузка памяти контейнеров
*Max Concurrent Requests* - Максимальное количество одновременных запросов
Вывод: по метрикам видим, что было сделано несколько запросов, на которые был быстро получен ответ. Загрузка памяти контейнеров достигла 18%. После того как был сделан запрос, некоторое время система держитконтейнер в статусе "idle", а затем выключает для экономии ресурсов. 
![](https://github.com/STAM1-lab/2024_2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-aminov_s_o/blob/main/lab2/lab2_screenshots/img4.jpg)

**5. Меняем порт на 8090**
Видим что система работает. 
![](https://github.com/STAM1-lab/2024_2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-aminov_s_o/blob/main/lab2/lab2_screenshots/img5.jpg)

**6. Настраиваем распределение трафика между двумя нашими версиями**
Функция позволяет определить как система будет распределять входящий трафик между версиями.
![](https://github.com/STAM1-lab/2024_2025-cloud-platforms-as-the-basis-of-technology-entrepreneurship-U4225-aminov_s_o/blob/main/lab2/lab2_screenshots/img6.jpg)
