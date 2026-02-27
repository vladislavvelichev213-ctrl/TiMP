# Отчет по лабораторной работе №1
## Тема: Изучение утилит для разработки проектов

**Выполнил:** Величев Владислав (ИУ8-21)  
**Дата выполнения:** 26.02.2025  
**Среда выполнения:** Linux (Ubuntu) на виртуальной машине  
**Репозиторий с файлами:** https://github.com/vladislavvelichev213-ctrl/TiMP

---

## 1. Выполнение туториала

### 1.1. Проверка окружения

**Команда:**
```bash
cmake --version
```
**Вывод:**
```
Command 'cmake' not found, but can be installed with:
sudo apt install cmake
```
*Комментарий: утилита cmake не установлена*

**Команда:**
```bash
curl --version
```
**Вывод:**
```
Command 'curl' not found, but can be installed with:
sudo apt install curl
```
*Комментарий: curl отсутствует*

**Команда:**
```bash
git --version
```
**Вывод:**
```
git version 2.51.0
```
*Комментарий: Git установлен*

**Команда:**
```bash
g++ --version
```
**Вывод:**
```
g++ (Ubuntu 15.2.0-4ubuntu4) 15.2.0
```
*Комментарий: компилятор G++ установлен*

**Команда:**
```bash
make --version
```
**Вывод:**
```
GNU Make 4.4.1
```
*Комментарий: утилита make установлена*

**Команда:**
```bash
tree --version
```
**Вывод:**
```
Command 'tree' not found, but can be installed with:
sudo apt install tree
```
*Комментарий: tree не установлен*

**Команда:**
```bash
wget --version
```
**Вывод:**
```
GNU Wget 1.25.0 built on linux-gnu.
```
*Комментарий: wget установлен*

**Команда:**
```bash
openssl version
```
**Вывод:**
```
OpenSSL 3.5.3 16 Sep 2025 (Library: OpenSSL 3.5.3 16 Sep 2025)
```
*Комментарий: OpenSSL установлен*

---

### 1.2. Настройка переменных окружения

**Команда:**
```bash
export GITHUB_USERNAME=vladislavvelichev213-ctrl
export GIST_TOKEN=ghp_GajXaF...
alias edit=nano
```

**Команда:**
```bash
echo $GITHUB_USERNAME
```
**Вывод:**
```
vladislavvelichev213-ctrl
```

**Команда:**
```bash
echo $GIST_TOKEN | cut -c1-10
```
**Вывод:**
```
ghp_GajXaF
```

**Команда:**
```bash
alias
```
**Вывод:**
```
edit='nano'
```

---

### 1.3. Создание структуры директорий

**Команда:**
```bash
mkdir -p ${GITHUB_USERNAME}/workspace
cd ${GITHUB_USERNAME}/workspace
pwd
```
**Вывод:**
```
/home/ubuntu/vladislavvelichev213-ctrl/workspace
```

**Команда:**
```bash
cd ..
pwd
```
**Вывод:**
```
/home/ubuntu/vladislavvelichev213-ctrl
```

**Команда:**
```bash
mkdir -p workspace/tasks/
mkdir -p workspace/projects/
mkdir -p workspace/reports/
cd workspace
pwd
```
**Вывод:**
```
/home/ubuntu/vladislavvelichev213-ctrl/workspace
```

---

### 1.4. Установка Node.js

**Команда:**
```bash
sudo apt update
sudo apt install nodejs npm -y
node --version
```
**Вывод:**
```
v20.19.4
```

**Команда:**
```bash
npm --version
```
**Вывод:**
```
10.8.2
```

**Команда:**
```bash
sudo ln -s /usr/bin/nodejs /usr/local/bin/node
```

---

### 1.5. Создание скрипта activate

**Команда:**
```bash
mkdir scripts
cat > scripts/activate<<EOF
export PATH=\${PATH}:`pwd`/node/bin
EOF
source scripts/activate
```

---

### 1.6. Установка gist

**Команда:**
```bash
sudo apt install ruby-full -y
sudo gem install gist
```
**Вывод:**
```
Successfully installed gist-6.0.0
Parsing documentation for gist-6.0.0
Done installing documentation for gist after 0 seconds
1 gem installed
```

**Команда:**
```bash
(umask 0077 && echo ${GIST_TOKEN} > ~/.gist)
cat ~/.gist | cut -c1-10
```
**Вывод:**
```
ghp_GajXaF
```

---

### 1.7. Клонирование лабораторной работы

**Команда:**
```bash
export LAB_NUMBER=01
git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
```
**Вывод:**
```
Cloning into 'tasks/lab01'...
remote: Enumerating objects: 12, done.
remote: Counting objects: 100% (12/12), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 12 (delta 2), reused 7 (delta 1), pack-reused 0
Receiving objects: 100% (12/12), done.
Resolving deltas: 100% (2/2), done.
```

**Команда:**
```bash
mkdir reports/lab${LAB_NUMBER}
cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
cd reports/lab${LAB_NUMBER}
pwd
```
**Вывод:**
```
/home/ubuntu/vladislavvelichev213-ctrl/workspace/reports/lab01
```

---

## 2. Выполнение домашнего задания

### Задание 1. Скачать библиотеку boost

**Команда:**
```bash
cd ~
wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
```
**Вывод:**
```
--2026-02-26 22:31:19--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
Распознаётся sourceforge.net (sourceforge.net)… 104.18.12.149, 104.18.13.149
Подключение к sourceforge.net (sourceforge.net)|104.18.12.149|:443... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа… 301 Moved Permanently
Адрес: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/ [переход]
--2026-02-26 22:31:19--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/
Повторное использование соединения с sourceforge.net:443.
HTTP-запрос отправлен. Ожидание ответа… 301 Moved Permanently
Адрес: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download [переход]
--2026-02-26 22:31:19--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download
Повторное использование соединения с sourceforge.net:443.
HTTP-запрос отправлен. Ожидание ответа… 302 Found
Адрес: https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABpmyplJ4MwBZjjhwNabi1OV8jsKZqjRlOS-JJiJ8CJlt2ELGnTd1WeLsRVFpIO5RX7lvD_Yz7Ycnl0GeSPpBfiZko_5A%3D%3D&use_mirror=unlimited&r= [переход]
--2026-02-26 22:31:19--  https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABpmyplJ4MwBZjjhwNabi1OV8jsKZqjRlOS-JJiJ8CJlt2ELGnTd1WeLsRVFpIO5RX7lvD_Yz7Ycnl0GeSPpBfiZko_5A%3D%3D&use_mirror=unlimited&r=
Распознаётся downloads.sourceforge.net (downloads.sourceforge.net)… 104.18.12.149, 104.18.13.149
Подключение к downloads.sourceforge.net (downloads.sourceforge.net)|104.18.12.149|:443... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа… 302 Found
Адрес: https://unlimited.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?viasf=1 [переход]
--2026-02-26 22:31:19--  https://unlimited.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?viasf=1
Распознаётся unlimited.dl.sourceforge.net (unlimited.dl.sourceforge.net)… 185.119.90.247
Подключение к unlimited.dl.sourceforge.net (unlimited.dl.sourceforge.net)|185.119.90.247|:443... соединение установлено.
HTTP-запрос отправлен. Ожидание ответа… 200 OK
Длина: 111710205 (107M) [application/x-gzip]
Сохранение в: ‘boost_1_69_0.tar.gz’

boost_1_69_0.tar.gz 100%[=================================================>] 106.53M  5.60MB/s    за 18s

2026-02-26 22:31:19 (5.60 MB/s) - ‘boost_1_69_0.tar.gz’ saved [111710205/111710205]
```

---

### Задание 2. Разархивировать boost

**Команда:**
```bash
tar -xzf boost_1_69_0.tar.gz
```

---

### Задание 3. Подсчет файлов без вложенных директорий

**Команда:**
```bash
find ~/boost_1_69_0 -maxdepth 1 -type f | wc -l
```
**Вывод:**
```
16
```

---

### Задание 4. Подсчет файлов с вложенными директориями

**Команда:**
```bash
find ~/boost_1_69_0 -type f | wc -l
```
**Вывод:**
```
62110
```

---

### Задание 5. Подсчет по типам файлов

**Заголовочные файлы (.h, .hpp, .hxx):**
```bash
find ~/boost_1_69_0 -type f \( -name "*.h" -o -name "*.hpp" -o -name "*.hxx" \) | wc -l
```
**Вывод:**
```
15208
```

**Файлы .cpp:**
```bash
find ~/boost_1_69_0 -type f -name "*.cpp" | wc -l
```
**Вывод:**
```
13789
```

**Остальные файлы:**
```bash
find ~/boost_1_69_0 -type f ! \( -name "*.h" -o -name "*.hpp" -o -name "*.hxx" -o -name "*.cpp" \) | wc -l
```
**Вывод:**
```
33113
```

---

### Задание 6. Поиск файла any.hpp

**Команда:**
```bash
find ~/boost_1_69_0 -name "any.hpp" -type f
```

**Полный список:** [`any_list.txt`](https://github.com/vladislavvelichev213-ctrl/TiMP/blob/main/any_list.txt)

---

### Задание 7. Поиск упоминаний boost::asio

**Команда:**
```bash
grep -r "boost::asio" ~/boost_1_69_0 | wc -l
```
**Вывод:**
```
17424
```

**Полный список:** [`asio_list.txt`](https://github.com/vladislavvelichev213-ctrl/TiMP/blob/main/asio_list.txt)

---

### Задание 8. Компиляция boost

**Команда:**
```bash
cd ~/boost_1_69_0
./bootstrap.sh
```
**Вывод:**
```
Building Boost.Build engine with toolset gcc...
tools/build/src/engine/bin.linuxx86_64/b2
Unicode/ICU support for Boost.Regex?... not found.
Generating Boost.Build configuration in project-config.jam...
Bootstrapping is done. To build, run:
    ./b2
```

**Команда:**
```bash
./b2
```
**Итог:**
```
...updated 1180 targets...
```

**Полный лог компиляции:** [`compilation.log`](https://github.com/vladislavvelichev213-ctrl/TiMP/blob/main/compilation.log)

---

### Задание 9. Перенос библиотек

**Команда:**
```bash
mkdir -p ~/boost-libs
find ~/boost_1_69_0 -name "*.a" -o -name "*.so" 2>/dev/null | xargs -I {} cp {} ~/boost-libs/
```

---

### Задание 10. Размер каждого файла

**Команда:**
```bash
du -sh ~/boost-libs/*
```

**Полный список:** [`lib_sizes.txt`](https://github.com/vladislavvelichev213-ctrl/TiMP/blob/main/lib_sizes.txt)

---

### Задание 11. Топ-10 самых тяжелых файлов

**Команда:**
```bash
du -sh ~/boost-libs/* | sort -rh | head -10
```
**Вывод:**
```
4.8M    /home/ubuntu/boost-libs/libboost_wave.a
3.8M    /home/ubuntu/boost-libs/libboost_math_tr1.a
3.5M    /home/ubuntu/boost-libs/libboost_math_tr1l.a
3.0M    /home/ubuntu/boost-libs/libboost_math_tr1f.a
2.8M    /home/ubuntu/boost-libs/libboost_regex.a
2.5M    /home/ubuntu/boost-libs/libboost_unit_test_framework.a
2.5M    /home/ubuntu/boost-libs/libboost_test_exec_monitor.a
2.2M    /home/ubuntu/boost-libs/libboost_locale.a
1.7M    /home/ubuntu/boost-libs/libboost_program_options.a
1.4M    /home/ubuntu/boost-libs/libboost_serialization.a
```

**Команда:**
```bash
du -sh ~/boost-libs
```
**Вывод:**
```
43M    /home/ubuntu/boost-libs
```

---

## 3. Публикация отчета

**Команда:**
```bash
cd ~/vladislavvelichev213-ctrl/workspace/reports/lab01
gist REPORT.md
```
**Вывод:**
```
https://gist.github.com
```

**Ссылка на отчет:** https://gist.github.com/vladislavvelichev213-ctrl/ff112b0f864d12ddb49accdca6c70abd

---

## 4. Выводы

| Категория | Количество |
|-----------|------------|
| Всего файлов в boost | 62 110 |
| Заголовочных файлов | 15 208 |
| Файлов .cpp | 13 789 |
| Прочих файлов | 33 113 |
| Упоминаний boost::asio | 17 424 |

Скомпилировано **1180 компонентов** библиотеки boost.  
Общий размер библиотек: **43 МБ**.  
Самая тяжелая: **libboost_wave.a** (4.8 МБ).

Все большие листинги вынесены в отдельные файлы в репозитории.
```


