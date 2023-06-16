FROM python:3.8-bookworm

WORKDIR /app

ADD . /app

RUN pip install -r requirements.txt
RUN pip install --upgrade Jinja2
RUN pip install -U flask

CMD ["uwsgi", "app.ini"]