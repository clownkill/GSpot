FROM python:3.11-alpine

WORKDIR /payments/apps

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN apk update \
    && apk add postgresql-dev \
    gcc python3-dev musl-dev

RUN pip install --upgrade pip

COPY ./requirements.txt ./

RUN pip install --no-cache-dir \
    -r requirements.txt

COPY . .

CMD [ "python", "./manage.py" ]