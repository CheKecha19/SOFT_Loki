# SOFT_Loki

Т.к. Loki можно запускать из командной строки, подгружать сюда файлы не буду.

## Инструкция по установке

```
# обновляем систему + доустанавливаем необходимые пакеты.
# могут возникать ошибки из-за уникальных особенностей систем, скрипт универсален насколько это возможно
sudo apt-get update && sudo apt-get upgrade -y
sudo pip2 install psutil netaddr pylzma colorama
sudo pip3 install psutil netaddr pylzma colorama
# sudo apt-get install НЕОБХОДИМО НАЗВАНИЕ ПАКЕТА
git clone https://github.com/Neo23x0/Loki
cd Loki/
sudo pip3 install rfc5424-logging-handler
sudo python3 loki-upgrader.py
sudo python3 loki.py --update
```

## Запуск проверки на локальном хосте

Актуально для текущего диска, на который установлен Loki

```
sudo python3 loki.py -l loki-report.txt
```

## Запуск на конкретном диске

Запуск проверки на конкретном диске. Перед запуском необходимо подмонтировать нужный диск

```
sudo python3 loki.py -p [путь к проверяемому диску] -l loki-report.txt
```

## Монтирование диска

```
# сначала находим нужный нам диск/раздел диска
sudo fdisk -l
# далее монтируем этот диск в определённую директорию
sudo mount /dev/sdb123 ./folder
# где
#/dev/sdb123 - нужный нам раздел диска
#./folder - папка, куда монтируем
```
