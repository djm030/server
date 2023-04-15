FROM python:3.8-slim-buster
ENV PYTHONUNBUFFERED 1
WORKDIR /app
COPY . /app/
COPY poetry.lock pyproject.toml /app/

RUN pip install --no-cache-dir --upgrade pip \
    && pip install --no-cache-dir poetry \
    && groupadd -r mygroup && useradd -r -g mygroup myuser

RUN poetry config virtualenvs.create false \
    && poetry install --no-interaction --no-ansi

RUN apt-get -y update \
    && apt-get -y install vim

EXPOSE 8000
USER myuser
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "config.wsgi:application"]