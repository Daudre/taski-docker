# FROM ghcr.io/astral-sh/uv:latest AS builder
FROM python:3.12

WORKDIR /app

RUN pip install gunicorn==25.3.0

COPY requirements.txt .

RUN pip install -r requirements.txt --no-cache-dir

# RUN uv init
# RUN uv add -r requirements.txt

COPY . .

# RUN apt update && apt -y install zip
# RUN zip arch.zip file.txt

# CMD ["python", "manage.py", "runserver", "0:8000"]
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]

