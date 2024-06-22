# 13-3 Стасенко Григорий Домашнее задание к занятию «Защита сети» 13-3

## Задание 1
Проведите разведку системы и определите, какие сетевые службы запущены на защищаемой системе:

sudo nmap -sA < ip-адрес >

sudo nmap -sT < ip-адрес >

sudo nmap -sS < ip-адрес >

sudo nmap -sV < ip-адрес >

По желанию можете поэкспериментировать с опциями: https://nmap.org/man/ru/man-briefoptions.html.

В качестве ответа пришлите события, которые попали в логи Suricata и Fail2Ban, прокомментируйте результат.

---
![image](https://github.com/Nightnek/HW13-3/assets/127677631/62c692a4-5190-4590-9694-009cdc5119d0)

Suricata заметала сканирование, Fail2Ban промолчал:
![image](https://github.com/Nightnek/HW13-3/assets/127677631/38bd47b3-a2cf-4019-9dd2-a5ca2fb1dab1)

---

## Задание 2
Проведите атаку на подбор пароля для службы SSH:

hydra -L users.txt -P pass.txt < ip-адрес > ssh

Настройка hydra:
создайте два файла: users.txt и pass.txt;
в каждой строчке первого файла должны быть имена пользователей, второго — пароли. В нашем случае это могут быть случайные строки, но ради эксперимента можете добавить имя и пароль существующего пользователя.
Дополнительная информация по hydra: https://kali.tools/?p=1847.

Включение защиты SSH для Fail2Ban:
открыть файл /etc/fail2ban/jail.conf,
найти секцию ssh,
установить enabled в true.
Дополнительная информация по Fail2Ban:https://putty.org.ru/articles/fail2ban-ssh.html.

В качестве ответа пришлите события, которые попали в логи Suricata и Fail2Ban, прокомментируйте результат.

---
![image](https://github.com/Nightnek/HW13-3/assets/127677631/af9185a9-ae10-404e-a9d5-8248d689ef55)

Suricata молчит, Fail2Ban забанил IP-адрес "злоумышленника"

![image](https://github.com/Nightnek/HW13-3/assets/127677631/9316c714-164e-4806-880c-f14eeed2843b)

---
