FROM python:3.7-slim

RUN mkdir /app

COPY api_yamdb/requirements.txt /app

RUN pip install -r /app/requirements.txt --no-cache-dir

COPY api_yamdb/ /app

WORKDIR /app

LABEL LABEL author='egorfedotovarz@gmail.com' version=1 broken_keyboards=0

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]

