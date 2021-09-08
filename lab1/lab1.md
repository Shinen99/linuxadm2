1. Назовите основные отличия и преимущества systemd от sysvinit, опишите подходы.
 - sysvinit запускает процессы последовательно исходя из фазы загрузки
 - systemd сначала исполняет default.target, а затем строит дерево зависимостей
 - systemd поддерживает активацию сервисов на основе сокетов
 - в sysvinit система runlevel, в systemd target
2. Каким образом происходит параллельный запуск всех процессов но в то же время сервисы стартуют с нужными зависимостями друг относительно друга
 - systemd по дереву зависимостей определяет необходимые для запуска демона сервисы и запускает их параллельно.
3. каким образом проверить работает процесс в sysvinit и в systemd?
 - sysvinit: chkconfig service_name
 - systemd: systemctl status unit
4. Как добавить в автозагрузку init скрипт в sysvinit и в systemd?
 - sysvinit: добавить скрипт в директорию /etc/init.d и выполнить chkconfig service_name on
 - systemd: добавить файл в /etc/systemd/system и выполнить systemctl enable service_name
5. Как посмотреть логи в системе systemd по нужному нам процесс  
   journalctl -u service_name
   
   
