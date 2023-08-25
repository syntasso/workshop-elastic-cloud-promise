FROM "alpine"
WORKDIR /pipeline

RUN apk update && apk add --no-cache bash curl openssl yq
RUN curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 \
    && chmod +x get_helm.sh && ./get_helm.sh

ADD run /pipeline/run
ADD beats-values.yaml /pipeline/beats-values.yaml
ADD default-config.yaml /pipeline/default-config.yaml

RUN chmod +x /pipeline/run

CMD [ "sh", "-c", "/pipeline/run" ]
ENTRYPOINT []