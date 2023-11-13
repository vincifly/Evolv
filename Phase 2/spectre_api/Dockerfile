
FROM ubuntu:20.04


RUN apt-get update && \
    apt-get install -y \
    python3 \
    python3-pip \
    git


RUN git clone https://gitlab.com/spectre.app/api.git /opt/spectre-api


WORKDIR /opt/spectre-api


RUN python3 -m venv /opt/spectre-api/venv


ENV PATH="/opt/spectre-api/venv/bin:${PATH}"


COPY requirements.txt /opt/spectre-api/
RUN pip3 install -r requirements.txt


COPY spectre-api-config.tmpl /opt/spectre-api/


CMD ["python3", "app.py"]
