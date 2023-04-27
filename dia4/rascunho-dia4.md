

# DIA 4 - PLATFORM ENGINEER SUMMIT 2023

git status
git add .
git commit -m "DIA 4 - PLATFORM ENGINEER SUMMIT 2023"
eval $(ssh-agent -s)
ssh-add /home/fernando/.ssh/chave-debian10-github
git push
git status



19:00 - 19:45
Matheus Fidelis - Sobrevivendo a Cenários de Caos com Istio Service Mesh

20:00 - 20:45
Yuri Sa - Auto-Observabilidade: Monitorando sua app NodeJS

21:00 - 21:45
Tainara Almeida - TBD

22:00 - 22:45
Willian dos Santos - Landing Zones: Desbloqueando o Poder da Infra-estrutura Modular, Escalável e Confiável







19:00 - 19:45
## Matheus Fidelis - Sobrevivendo a Cenários de Caos com Istio Service Mesh

## Envoy Proxy

- Envoy é MUITO IMPORTANTE.

- Envoy é um proxy reverso.
é um intermediador entre o Servidor

- 









20:00 - 20:45
## Yuri Sa - Auto-Observabilidade: Monitorando sua app NodeJS

operatorhub.io

## Auto-instrumentação

- O OpenTelemetry entra como um "init-container".

- Envia pro Collector


- A Auto-instrumentação é realizada baseada nos annotations.

- Repo
https://github.com/yuriolisa/pes-2023-opentelemetry





Deploy das Ferramentos de Observabilidade:

    Grafana
    Loki
    Mimir
    Tempo

kubectl apply -f 01-backend.yaml

    Você pode verificar se o serviços estão rodando através do comando kubectl get pods -n observability-backend e o resultado deve ser esse:

NAME                              READY   STATUS    RESTARTS   AGE
grafana-5bcfcc785d-lw8b5          1/1     Running   0          5h38m
loki-0                            1/1     Running   0          5h38m
mimir-0                           1/1     Running   0          5h38m
tempo-7cd894b88f-tkk8j            1/1     Running   0          5h38m

    Abra uma conexão com o serviço do Grafana em uma outra sessão do terminal:

kubectl port-forward -n observability-backend svc/grafana 3000:3000



LOKI
Loki is a log aggregation

TEMPO
Grafana Tempo is an open source, easy-to-use, and high-scale distributed tracing backend. 

MIMIR
Grafana Mimir is an open source, horizontally scalable, highly available, multi-tenant, long-term storage for Prometheus.



- Este trecho de código abaixo define que os Logs sejam enviados ao Loki, os Traces sejam enviados ao Tempo e as métricas sejam enviadas ao Mimir:

~~~~YAML
exporters:
      otlp:
        endpoint: "http://tempo.observability-backend.svc.cluster.local:55680"
        tls:
          insecure: true
      otlphttp/mimir:
        endpoint: "http://mimir.observability-backend.svc.cluster.local:8080/otlp"
      loki:
        endpoint: "http://loki.observability-backend.svc.cluster.local:3100/loki/api/v1/push"
      logging:
~~~~




