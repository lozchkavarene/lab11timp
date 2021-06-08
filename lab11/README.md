# Отчет по лабораторной работе № 11

### Цель работы

Данная лабораторная работа посвещена изучению процесса создания сеансов совместной разработки с использованием инструмента **ngrok**

### Задания

- [x] 1. Ознакомиться со ссылками учебного материала
- [x] 2. Выполнить инструкцию учебного материала
- [x] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Выполнение инструкции учебного материала

Установка tmux и ngrok

```sh
$ pacman -S tmux 
$ git clone https://aur.archlinux.org/ngrok.git
$ makepkg -si
```

Запуск сессии tmux:

```sh
$ tmux new -s session_with_group
```

Открытие туннеля на localhost на 22 порт (стандартный для ssh)

```sh
# Me:
$ ngrok authtoken 1sFy5Q...ynp5
    Authtoken saved to configuration file: /home/orm/.ngrok2/ngrok.yml

$ ngrok tcp 22
```

```sh
# Some other person:
$ ssh serpentian@2.tcp.ngrok.io -p 13829
$ tmux a -t session_with_group
```

![ssh](img/ssh.png)

### Ссылки

- [Tmux](https://raw.githubusercontent.com/tmux/tmux/master/README)
- [Libevent](http://libevent.org)
- [Ncurses](http://invisible-island.net/ncurses/)
