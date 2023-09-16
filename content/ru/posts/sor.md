---
title: "sot tool"
date: 2015-05-27
description: ""
featured_image: ""
tags: ["#linux", "#tool", "#monitoring"]
draft: false
---

## sor - универсальная утилита для мониторинга процессов в реальном времени

Итак в центре внимания sar - многофункциональная утилита, для полноценного анализа системы. Входит в пакет sysstat.

sysstat – удобная утилита для измерения и анализа производительности системы. Помимо sar 

1) Для начала работы необходимо отредактировать файл /etc/default/sysstat изменив строку 
change ENABLED=”false” 
на 
change ENABLED=”true”
2) Затем изменить в crontab интервал c 10 минут
5-55/10 * * * * root command -v debian-sa1 > /dev/null && debian-sa1 1 1
на желаемое значение. В примере на 2 минуты. Подробнее о cron - https://ru.wikipedia.org/wiki/Cron
*/2 * * * * root command -v debian-sa1 > /dev/null && debian-sa1 1 1
3) Перезапустить sysstat командой 
service sysstat restart или /etc/init.d/sysstat restart

Экскурс в историю для любознательных.


При использовании различных ключей и их комбинаций способна показывать более чем достаточную информацию о необходимых ресурсах системы, умеет «возвращаться в прошлое», однако не подходит для анализа конкретного процесса (для этого можно использовать pidstat <номер процесса>).

В этой статье будут рассмотрены примеры команд для анализа различных процессов системы.

Стандартный вывод sar без использования ключей показывает активность процессора и выглядит примерно так:

Linux 3.2.0-4-amd64 (user) 	17.12.2014 	_x86_64_	(4 CPU)

03:02:01        CPU     %user     %nice   %system   %iowait    %steal     %idle
03:03:01        all     10,30      0,06      2,93      2,10      0,00     84,60
03:04:01        all     12,76      0,27      3,73      3,79      0,00     79,45
03:05:01        all     13,38      0,51      4,75      5,08      0,00     76,27
03:06:01        all     13,83      0,44      4,43      3,62      0,00     77,68
Среднее:     all     12,57      0,32      3,96      3,65      0,00     79,51

%usr: - процент процессорного времени, потраченного на пользовательские процессы, такие как приложения, сценарии оболочки или взаимодействие с пользователем.
%sys: - процент процессорного времени, потраченного на выполнение задач ядра.
%wio: - процент процессорного времени, затраченного на ожидание ввода-вывода в/из блочных устройств, например, жесткого диска. 
%idle: - процент времени, которое процессор простаивал.


А теперь о работе с sar как с инструментом или гибкое использование ключей.

sar -A  выведет всю статистику по всем процессорам. Не стоит исподьзовать эту опцию для поиска и просмотра данных, только если Вы не любитель смотреть на постыню из циферок.

sar -u даст статистику о работе системы за день.

sar -r покажет статистику использования памяти

sar -P ALL сообщит информацию по всем ядрам, тогда как например sar -P 1 1 1 покажет по 1 конкретному ядру

sar -p -d 1 1 для статистики по блочным устройствам

sar -b показывает информацию о буферах и эффективности использования буфера в сравнении с диском.

sar -d соберет I/O статистику (активность диска)

sar -n KEY для анализа сети, где вместо KEY может быть ALL - все параметры, DEV - статус eth0, eth1 ... UDP, TCP, - информация о udp, tsp трафике соответственно. И другие.

sar -q вывод load average и очередях

Вывести 4 состояния CPU с интервалом в 1 секунду может
sar 1 4

Несмотря на то, что sar в основном интересен как инструмент для оценки текущего состояния системы, от сохраняет свои данные в каталог var/log/sysstat/

Команда 
sar -f /var/log/sysstat/sa05
Выведет информацию собранную sar за 5 исло текущего месяца.

Если Вы хотите записать вывод программы для дальнейшего анализа в файл:
sar -A > $(date +`hostname`-%d-%m-%y-%H%M.log)

Ключи, конечно же можно (и нужно) комбинировать для получения конкретной интересующей информации.
Так, например, sar -P 1 1 3 выведет три состояния текущего использования CPU для первого ядра с интервалом в 1 секунду.
А sar -r ALL -f /var/log/sa/sa10 отобразит информацию о свободной памяти за 10 день текущего месяца, которую возьмет из файла /var/log/sysstat/sa10 .

Помимо указаных здесь, каждый из ключей имеет собственные опции, используя которые можно получить еще более полную информацию о интересующих процессах. Прочитать о них и их использовании подробнее можно в дкументации к sar

Дополнительную информацию о программе и ключах Вы можете получить в документации.
man sar или info sar
man sysstat или info sysstat