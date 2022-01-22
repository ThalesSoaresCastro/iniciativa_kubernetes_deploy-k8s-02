FROM python:3.9

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

WORKDIR /code

RUN python -m pip install --upgrade pip

COPY requirements.txt /code/

RUN pip install -r requirements.txt

COPY . /code/

RUN ls -a

EXPOSE 5000

CMD ["gunicorn", "--workers=3", "--bind", "0.0.0.0:5000", "-c","config.py", "app:app" ]

