FROM python:3.11-slim

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

WORKDIR /app

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*


COPY requirements.txt /app/
RUN pip install --no-cache-dir --upgrade pip && pip install -r requirements.txt


COPY . /app/

CMD ["python", "manage.py", "runserver", "0.0.0.0:8001"]

EXPOSE 8001

