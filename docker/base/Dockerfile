ARG cert_image
ARG root_image

FROM $cert_image AS cert
RUN export http_proxy=http://10.202.52.178:1080 && \
    export https_proxy=http://10.202.52.178:1080 && \
    apk add --update --no-cache ca-certificates

FROM $root_image
COPY --from=cert /etc/ssl/certs/ca-certificates.crt /etc/ssl/certs/ca-certificates.crt
