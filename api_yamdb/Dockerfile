FROM python:3.7-slim

WORKDIR /app

COPY api_yamdb/requirements.txt .

RUN pip install -r requirements.txt --no-cache-dir

COPY api_yamdb/ .

LABEL LABEL author='egorfedotovarz@gmail.com' version=1 broken_keyboards=0

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]