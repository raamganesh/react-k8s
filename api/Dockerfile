FROM python:3.11-slim

RUN apt-get update \
    && apt-get install -y --no-install-recommends --no-install-suggests \
    build-essential default-libmysqlclient-dev pkg-config\
    && pip install --no-cache-dir --upgrade pip

WORKDIR /app
COPY ./api/requirements.txt /app
RUN pip install --no-cache-dir --requirement /app/requirements.txt
COPY ./api /app

EXPOSE 5000

CMD ["python3", "app.py"]