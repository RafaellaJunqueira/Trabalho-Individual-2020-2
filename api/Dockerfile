# Origem do tipo imagem que esse docker vai ter 
FROM python:3
ENV PYTHONUNBUFFERED 1
ENV PYTHONDONTWRITEBYTECODE 1

RUN apt-get update
RUN apt install -y netcat

ARG DJANGO_ALLOWED_HOSTS
ARG DJANGO_SECRET_KEY
ARG DJANGO_CORS_ORIGIN_WHITELIST

ENV DJANGO_ALLOWED_HOSTS $DJANGO_ALLOWED_HOSTS
ENV DJANGO_SECRET_KEY $DJANGO_SECRET_KEY
ENV DJANGO_CORS_ORIGIN_WHITELIST $DJANGO_CORS_ORIGIN_WHITELIST

RUN mkdir /backend
WORKDIR /backend
# copiar o projeto local pra imagem do conteiner
ADD . /backend/
COPY requirements.txt manage.py api task /backend/

# comandos de instalação
RUN pip install -r requirements.txt
RUN apt-get update

# Qual porta será utilizada
EXPOSE 8000
EXPOSE 5432