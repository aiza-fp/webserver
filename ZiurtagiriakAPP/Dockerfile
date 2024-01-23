FROM python:3.8-slim

WORKDIR /app

COPY requirements.txt .

ENV PYTHONPATH=/app

RUN pip install --no-cache-dir -r requirements.txt

RUN pip show gunicorn 
RUN pyenv which gunicorn
RUN which gunicorn

COPY . .

CMD ["gunicorn", "-w", "4", "-b", "0.0.0.0:5000", "wsgi:app"]
