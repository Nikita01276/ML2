Ноутбуки по машинному обучению
==============================

# ⚠ ЭТО ИЗДАНИЕ УСТАРЕЛО. УЖЕ ДОСТУПНО <a href="https://github.com/ageron/handson-ml3">ТРЕТЬЕ ИЗДАНИЕ МОЕЙ КНИГИ</a>, А ТАКЖЕ <a href="https://github.com/ageron/handson-mlp">ВЕРСИЯ НА PYTORCH</a> И <a href="https://homl.info/">МНОЖЕСТВО ПЕРЕВОДОВ</a>.

Этот проект относится ко второму изданию, которое уже устарело (оно вышло в 2019 году).

> **О переводе.** Это неофициальный перевод текстовых ячеек ноутбуков, комментариев в коде и файлов документации на русский язык. Сам код (включая строки внутри кода) оставлен без изменений, поэтому все примеры работают так же, как в оригинале.

<details>

Цель этого проекта — научить вас основам машинного обучения на
Python. Он содержит код примеров и решения упражнений второго издания моей книги издательства O'Reilly [Hands-on Machine Learning with Scikit-Learn, Keras and TensorFlow](https://www.oreilly.com/library/view/hands-on-machine-learning/9781492032632/):

<img src="https://images-na.ssl-images-amazon.com/images/I/51aqYc1QyrL._SX379_BO1,204,203,200_.jpg" title="book" width="150" />

**Примечание**: если вам нужны ноутбуки первого издания, смотрите [ageron/handson-ml](https://github.com/ageron/handson-ml). Третье издание — в [ageron/handson-ml3](https://github.com/ageron/handson-ml3).

## Быстрый старт

### Хотите поэкспериментировать с ноутбуками онлайн, ничего не устанавливая?
Воспользуйтесь любым из следующих сервисов (я рекомендую Colab или Kaggle, поскольку они бесплатно предоставляют GPU и TPU).

**ВНИМАНИЕ**: _имейте в виду, что эти сервисы предоставляют временные среды: всё, что вы сделаете, через некоторое время будет удалено, поэтому обязательно скачивайте важные для вас данные._

* <a href="https://colab.research.google.com/github/ageron/handson-ml2/blob/master/" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

* <a href="https://homl.info/kaggle/"><img src="https://kaggle.com/static/images/open-in-kaggle.svg" alt="Open in Kaggle" /></a>

* <a href="https://mybinder.org/v2/gh/ageron/handson-ml2/HEAD?filepath=%2Findex.ipynb"><img src="https://mybinder.org/badge_logo.svg" alt="Launch binder" /></a>

* <a href="https://homl.info/deepnote/"><img src="https://deepnote.com/buttons/launch-in-deepnote-small.svg" alt="Launch in Deepnote" /></a>

### Хотите просто быстро посмотреть ноутбуки, не выполняя код?

* <a href="https://nbviewer.jupyter.org/github/ageron/handson-ml2/blob/master/index.ipynb"><img src="https://raw.githubusercontent.com/jupyter/design/master/logos/Badges/nbviewer_badge.svg" alt="Render nbviewer" /></a>

* [Встроенный просмотрщик ноутбуков github.com](https://github.com/ageron/handson-ml2/blob/master/index.ipynb) тоже работает, но он не идеален: он медленнее, математические формулы отображаются не всегда правильно, а большие ноутбуки часто не открываются.

### Хотите запустить проект с помощью образа Docker?
Прочитайте [инструкции по Docker](https://github.com/ageron/handson-ml2/tree/master/docker).

### Хотите установить проект на свою машину?

Начните с установки [Anaconda](https://www.anaconda.com/distribution/) (или [Miniconda](https://docs.conda.io/en/latest/miniconda.html)) и [git](https://git-scm.com/downloads), а если у вас есть GPU, совместимый с TensorFlow, установите [драйвер GPU](https://www.nvidia.com/Download/index.aspx) и подходящие версии CUDA и cuDNN (подробнее см. документацию TensorFlow).

Затем клонируйте проект: откройте терминал и введите следующие команды (не вводите знак `$` в начале каждой строки, он лишь показывает, что это команды терминала):

    $ git clone https://github.com/ageron/handson-ml2.git
    $ cd handson-ml2

Затем выполните следующие команды:

    $ conda env create -f environment.yml
    $ conda activate tf2
    $ python -m ipykernel install --user --name=python3

Наконец, запустите Jupyter:

    $ jupyter notebook

Если нужны дополнительные инструкции, прочитайте [подробные инструкции по установке](INSTALL.md).

# Частые вопросы (FAQ)

**Какую версию Python использовать?**

Я рекомендую Python 3.8. Если следовать приведённым выше инструкциям по установке, вы получите именно эту версию. Большая часть кода будет работать и с другими версиями Python 3, но некоторые библиотеки пока не поддерживают Python 3.9 или 3.10, поэтому я рекомендую Python 3.8.

**Я получаю ошибку при вызове `load_housing_data()`**

Убедитесь, что вызываете `fetch_housing_data()` *до* вызова `load_housing_data()`. Если вы получаете ошибку HTTP, убедитесь, что выполняете в точности тот же код, что и в ноутбуке (при необходимости скопируйте и вставьте его). Если проблема не исчезает, проверьте настройки сети.

**Я получаю ошибку SSL на MacOSX**

Вероятно, нужно установить SSL-сертификаты (см. этот [вопрос на StackOverflow](https://stackoverflow.com/questions/27835619/urllib-and-ssl-certificate-verify-failed-error)). Если вы скачали Python с официального сайта, выполните в терминале `/Applications/Python\ 3.8/Install\ Certificates.command` (замените `3.8` на установленную у вас версию). Если вы установили Python через MacPorts, выполните в терминале `sudo port install curl-ca-bundle`.

**Я установил проект локально. Как обновить его до последней версии?**

См. [INSTALL.md](INSTALL.md)

**Как обновить библиотеки Python до последних версий при использовании Anaconda?**

См. [INSTALL.md](INSTALL.md)

## Участники
Я хотел бы поблагодарить всех, [кто внёс вклад в этот проект](https://github.com/ageron/handson-ml2/graphs/contributors): присылал полезные отзывы, сообщал о проблемах или отправлял пул-реквесты. Особая благодарность Хэсону Паку (Haesun Park) и Иэну Борегару (Ian Beauregard), которые проверили каждый ноутбук и отправили множество пул-реквестов, в том числе помогли с некоторыми решениями упражнений. Спасибо также Стивену Банкли (Steven Bunkley) и Ziembla, создавшим каталог `docker`, и пользователю GitHub SuperYorio, который помог с некоторыми решениями упражнений.

</details>