FROM ubuntu:jammy-20240227

RUN apt update && \
    apt install -y python3.10 python3-pip git

WORKDIR /app

COPY ./docker/requirements.txt /app/requirements.txt

RUN pip install -r requirements.txt
RUN rm /app/requirements.txt

EXPOSE 8889
ENTRYPOINT ["jupyter", "notebook","--allow-root","--port=8889","--ip=0.0.0.0","--no-browser"]
