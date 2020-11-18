ARG PYTHON_VERSION
FROM python:${PYTHON_VERSION}

ARG PYTHON_VERSION
ENV PYTHONUNBUFFERED 1

WORKDIR /www

COPY ./pip.conf /root/.pip/pip.conf
COPY ./www/requirements.txt requirements.txt
RUN pip install --no-cache-dir -r /www/requirements.txt

COPY ./supervisor /etc/supervisor
run mkdir -p  /logs/supervisor

CMD [ "/usr/bin/supervisord", "-c", "/etc/supervisor/supervisord.conf" ]
