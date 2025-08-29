FROM python:3.12-slim

WORKDIR /app

COPY requirements.txt .
RUN python -m ensurepip && pip install --no-cache-dir setuptools wheel
RUN pip install gunicorn==23.0.0
RUN pip install -r requirements.txt --no-cache-dir


COPY . .

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]

