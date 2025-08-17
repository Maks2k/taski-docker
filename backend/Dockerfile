FROM python:3.12

WORKDIR /app

COPY requirements.txt .
RUN pip install gunicorn==23.0.0
RUN pip install -r requirements.txt --no-cache-dir
RUN python -m ensurepip && pip install --no-cache-dir setuptools wheel

COPY . .

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]