FROM python:3-alpine

# Temporary fix for https://github.com/jaegertracing/jaeger/issues/1494
RUN pip install urllib3==1.24.3

RUN export http_proxy=http://192.168.60.1:1080 && \
    export https_proxy=http://192.168.60.1:1080 && \
    pip install elasticsearch elasticsearch-curator
COPY esCleaner.py /es-index-cleaner/

ENTRYPOINT ["python3", "/es-index-cleaner/esCleaner.py"]
