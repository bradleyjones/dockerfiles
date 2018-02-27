FROM python:latest

WORKDIR /app
RUN git clone -b feature/auto_join https://github.com/okurz/pickups.git
RUN pip install -r /app/pickups/requirements.txt
WORKDIR /app/pickups
CMD python -m pickups --port 6667 --address 0.0.0.0
