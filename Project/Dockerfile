FROM python:3.9-alpine as builder

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONNUNBUFFERED 1

#psycopg2 dependencies installation
RUN apk update
RUN apk add postgresql-dev gcc python3-dev musl-dev libc-dev linux-headers

RUN apk add jpeg-dev zlib-dev libjpeg

RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip wheel --no-cache-dir --no-deps --wheel-dir /wheels -r requirements.txt

#### FINAL ####

FROM python:3.9-alpine

WORKDIR /app

COPY ./app .

RUN apk update && apk add libpq
COPY --from=builder ./wheels /wheels
COPY --from=builder ./requirements.txt .
RUN pip install --no-cache /wheels/*
#RUN pip install -r requirements.txt

COPY ./scripts /scripts
RUN chmod +x /scripts/*

#RUN mkdir -p /vol/media
#RUN mkdir -p /vol/static

#RUN adduser -S user

#RUN chown -R user /vol

#RUN chmod -R 755 /vol
#RUN chown -R user /app
#RUN chmod -R 755 /app

#USER user

ENTRYPOINT ["/scripts/entrypoint.sh"]