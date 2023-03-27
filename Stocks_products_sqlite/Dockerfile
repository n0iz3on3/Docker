FROM python:3.10

COPY ./requirements.txt /scr/requirements.txt
RUN pip3 install --no-cache-dir --upgrade -r /scr/requirements.txt

COPY . /src

WORKDIR /src

ENV MY_ENV=netology

EXPOSE 8000

CMD gunicorn stocks_products.wsgi -b 0.0.0.0:8000
