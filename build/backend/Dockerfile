FROM python:3.9


RUN apt update && apt install -y python3-venv && rm -rf /var/lib/apt/lists/*


WORKDIR /opt
RUN git clone https://github.com/dodgyturtle/star-burger.git

WORKDIR /opt/star-burger

RUN pip install -r requirements.txt
ENV YANDEX_GEO_APIKEY="BUILD_KEY"
ENV ROLLBAR_KEY="BUILD_KEY"
ENV ROLLBAR_ENV="BUILD_KEY"
ENV DB_URL="sqlite:///:memory:"
RUN python manage.py collectstatic --noinput
CMD ["cp", "-a", "/opt/star-burger/staticfiles/.", "/opt/frontend"]
