# Use a more recent base image with security patches
FROM python:3.10-slim-bookworm  # or latest available

LABEL MANTAINER="Seu Nome"

WORKDIR /app

COPY . /app

# Update system packages
RUN apt-get update && apt-get upgrade -y && apt-get clean

# Install dependencies
COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

EXPOSE 8000

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "app:app"]