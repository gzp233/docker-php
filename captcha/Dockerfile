
FROM python:3.9.10 as builder

ADD . /app/

WORKDIR /app/

COPY requirements.txt /app/

# timezone
ENV TZ=Asia/Shanghai

RUN pip install --no-cache-dir --upgrade pip \
     && pip install --no-cache-dir -r requirements.txt


ENTRYPOINT ["python3", "ocr_server.py"]
EXPOSE 6000