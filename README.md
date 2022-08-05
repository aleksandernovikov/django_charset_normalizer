# The issue was found in the Django project

[Martor](https://github.com/agusmakmun/django-markdown-editor)
uses  [charset_normalizer](https://github.com/ousret/charset_normalizer)

1. Clone this project
2. Create venv
3. Install requirements `pip install -r requirements.txt` to venv
4. Call Django command `python manage.py makemessages -l ru`
5. When calling the command `python manage.py makemessages -l ru`, for example. An error occurs.

```
xgettext: ./venv/lib/python3.8/site-packages/charset_normalizer/__init__.py:1: Кодировка "utf_8" неизвестна.  Продолжение работы с ASCII.
xgettext: Не ASCII-строка у ./venv/lib/python3.8/site-packages/charset_normalizer/__init__.py:12.
          Укажите входную кодировку с помощью параметра --from-code или с помощью
          комментария, как описано на http://www.python.org/peps/pep-0263.html.
```

If you fix the `utf_8` on the `utf-8` in the specified files, then the assembly of the messages is fine.
