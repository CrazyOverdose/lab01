## Laboratory work I

Данная лабораторная работа посвещена изучению утилит для разработки проектов

## Tasks

- [x] 1. Ознакомиться со ссылками учебного материала
- [x] 2. Выполнить инструкцию учебного материала
- [x] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial
Установка переменных окружения,создание другой версии команды
```bash
$ export GITHUB_USERNAME=СrazyOverdose
$ export GIST_TOKEN=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
$ alias edit=nano
```
Создание нового каталога, который станет рабочей областью
```
$ mkdir -p ${GITHUB_USERNAME}/workspace #команда для создания новых каталогов
$ cd ${GITHUB_USERNAME}/workspace       #изменение текущего рабочего каталога
$ pwd                                   #выводит полный путь от корневого 
                                        #каталога к текущему рабочему каталог                            
/home/absinthetoxin/СrazyOverdose/workspace
$ cd ..   #переход на директорию выше
$ pwd
/home/absinthetoxin/CrazyOverdose
```
Создание в уже созданном каталоге новых каталогов
```ShellSession
$ mkdir -p workspace/tasks/
$ mkdir -p workspace/projects/
$ mkdir -p workspace/reports/
$ cd workspace
```
Скачивание и распаковка nodejs в созданную рабочую область
```ShellSession
# Debian 
$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz                      
--2019-06-09 15:43:25--  https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz
Загружен сертификат CA «/etc/ssl/certs/ca-certificates.crt»
Распознаётся nodejs.org (nodejs.org)… 104.20.23.46, 104.20.22.46, 2606:4700:10::6814:162e, ...
Подключение к nodejs.org (nodejs.org)|104.20.23.46|:443... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа… 200 OK
Длина: 9356460 (8,9M) [application/x-xz]
Сохранение в: «node-v6.11.5-linux-x64.tar.xz»

node-v6.11.5-linux- 100%[===================>]   8,92M  8,73MB/s    за 1,0s    

2019-06-09 15:43:26 (8,73 MB/s) - «node-v6.11.5-linux-x64.tar.xz» сохранён [9356460/9356460]
$ tar -xf node-v6.11.5-linux-x64.tar.xz   #встроенный архиватор
$ rm -rf node-v6.11.5-linux-x64.tar.xz    #удаление файлов
$ mv node-v6.11.5-linux-x64 node          #утилита для перемещения/переименования файлов
```
Дописывание в PATH путь к скачанному nodejs
```ShellSession
$ ls node/bin       #утилита, которая печатает в стандартный вывод содержимое каталогов
node  npm
$ echo ${PATH}      #команда для отображения строки текста
/usr/local/bin:/usr/bin:/bin:/usr/local/sbin:/usr/lib/jvm/default/bin:
/usr/bin/site_perl:/usr/bin/vendor_perl:/usr/bin/core_perl
$ export PATH=${PATH}:`pwd`/node/bin  #команда командной оболочки UNIX, 
                                      #добавляющая переменную в среду окружения.
$ echo ${PATH}
/usr/local/bin:/usr/bin:/bin:/usr/local/sbin:/usr/lib/jvm/default/
bin:/usr/bin/site_perl:/usr/bin/vendor_perl:/usr/
bin/core_perl:/home/absinthetoxin/workspace/node/bin
$ mkdir scripts
$ cat > scripts/activate<<EOF #утилита UNIX, 
                              #выводящая последовательно указанные файлы (или устройства)
export PATH=\${PATH}:`pwd`/node/bin
EOF
$ source scripts/activate  #читает и выполняет команды из 
                           #указанного файла в командном процессоре
```
Скачивание gistup 
```ShellSession
$ npm install -g gistup                #скачивание пакета вручную
/home/absinthetoxin/workspace/node/bin/gistup -> 
/home/absinthetoxin/workspace/node/lib/node_modules/gistup/bin/gistup
/home/absinthetoxin/workspace/node/bin/gistup-open -> 
/home/absinthetoxin/workspace/node/lib/node_modules/gistup/bin/gistup-open
/home/absinthetoxin/workspace/node/bin/gistup-rename -> 
/home/absinthetoxin/workspace/node/lib/node_modules/gistup/bin/gistup-rename
/home/absinthetoxin/workspace/node/lib
└─┬ gistup@0.1.3 
  ├─┬ optimist@0.3.7 
  │ └── wordwrap@0.0.3 
  └── queue-async@1.2.1 
$ ls node/bin
gistup  gistup-open  gistup-rename  node  npm
```
Записывание текста в файл gistup.json 
```ShellSession
$ cat > ~/.gistup.json <<EOF
{
  "token": "${GIST_TOKEN}"
}
EOF
```

## Report

```ShellSession
$ export LAB_NUMBER=01
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gistup -m "lab${LAB_NUMBER}" # enter: yes↵
```

## Links

### Unix commands

- [ar](https://en.wikipedia.org/wiki/Ar_(Unix))
- [cat](https://en.wikipedia.org/wiki/Cat_(Unix))
- [cd](https://en.wikipedia.org/wiki/Cd_(command))
- [cp](https://en.wikipedia.org/wiki/Cp_(Unix))
- [cut](https://en.wikipedia.org/wiki/Cut_(Unix))
- [echo](https://en.wikipedia.org/wiki/Echo_(command))
- [env](https://en.wikipedia.org/wiki/Env_(shell))
- [ex](https://en.wikipedia.org/wiki/Ex_(editor))
- [file](https://en.wikipedia.org/wiki/File_(command))
- [find](https://en.wikipedia.org/wiki/Find)
- [ls](https://en.wikipedia.org/wiki/Ls)
- [man](https://en.wikipedia.org/wiki/Man_page)
- [mkdir](https://en.wikipedia.org/wiki/Mkdir)
- [mv](https://en.wikipedia.org/wiki/Mv)
- [nm](https://en.wikipedia.org/wiki/Nm_(Unix))
- [ps](https://en.wikipedia.org/wiki/Ps_(Unix))
- [pwd](https://en.wikipedia.org/wiki/Pwd)
- [rm](https://en.wikipedia.org/wiki/Rm_(Unix))
- [sed](https://en.wikipedia.org/wiki/Sed)
- [touch](https://en.wikipedia.org/wiki/Touch_(Unix))

### Package Managers

- [apt](http://help.ubuntu.ru/wiki/apt) | [dnf](https://en.wikipedia.org/wiki/DNF_(software)) | [yum](https://fedoraproject.org/wiki/Yum/ru)
- [brew](https://brew.sh) | [linuxbrew](http://linuxbrew.sh)
- [npm](https://docs.npmjs.com)

### Software

- [curl](https://www.gitbook.com/book/bagder/everything-curl/details)
- [wget](https://www.gnu.org/software/wget/manual/wget.pdf)
- [clang](https://clang.llvm.org)
- [g++](https://gcc.gnu.org/onlinedocs/gcc-4.0.2/gcc/G_002b_002b-and-GCC.html)
- [make](https://en.wikipedia.org/wiki/Make_(software))
- [open](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/open.1.html)
- [openssl](https://www.openssl.org)
- [nano](https://www.nano-editor.org)
- [tree](https://linux.die.net/man/1/tree)
- [vim](http://www.vim.org)

## Homework

1. Скачайте библиотеку *boost* с помощью утилиты **wget**. Адрес для скачивания `https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`.
2. Разархивируйте скаченный файл в директорию `~/boost_1_69_0`
3. Подсчитайте количество файлов в директории `~/boost_1_69_0` **не включая** вложенные директории.
4. Подсчитайте количество файлов в директории `~/boost_1_69_0` **включая** вложенные директории.
5. Подсчитайте количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`).
6. Найдите полный пусть до файла `any.hpp` внутри библиотеки *boost*.
7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.
8. Скомпилирутйе *boost*. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).
9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.
10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
11. Найдите *топ10* самых "тяжёлых".

```
Copyright (c) 2015-2019 The ISC Authors
```
