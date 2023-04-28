

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



- Forkeado
https://github.com/fernandomullerjr/pes-2023-opentelemetry





## Deploy das Ferramentos de Observabilidade:

https://github.com/fernandomullerjr/pes-2023-opentelemetry

    Grafana
    Loki
    Mimir
    Tempo

kubectl apply -f 01-backend.yaml

    Você pode verificar se o serviços estão rodando através do comando kubectl get pods -n observability-backend e o resultado deve ser esse:
~~~~bash
NAME                              READY   STATUS    RESTARTS   AGE
grafana-5bcfcc785d-lw8b5          1/1     Running   0          5h38m
loki-0                            1/1     Running   0          5h38m
mimir-0                           1/1     Running   0          5h38m
tempo-7cd894b88f-tkk8j            1/1     Running   0          5h38m
~~~~

    Abra uma conexão com o serviço do Grafana em uma outra sessão do terminal:

kubectl port-forward -n observability-backend svc/grafana 3000:3000



LOKI
Loki is a log aggregation

TEMPO
Grafana Tempo is an open source, easy-to-use, and high-scale distributed tracing backend. 

MIMIR
Grafana Mimir is an open source, horizontally scalable, highly available, multi-tenant, long-term storage for Prometheus.





kubectl port-forward -n observability-backend svc/grafana 3000:3000





## Instalação Opentelemetry Operator

    Instalação do CertManager como dependência do operator:

kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.11.0/cert-manager.yaml

    Instalação OpenTelemetry Operator:

kubectl apply -f https://github.com/open-telemetry/opentelemetry-operator/releases/download/v0.74.0/opentelemetry-operator.yaml

    Para verificar se a instalação do Operator ocorreu bem basta executar o seguinte comando substituindo o nome do pod kubectl logs -n opentelemetry-operator-system opentelemetry-operator-controller-manager-7487c6674d-shpbl:

~~~~bash
Defaulted container "manager" out of: manager, kube-rbac-proxy
{"level":"info","ts":"2023-04-27T11:28:16.807422088Z","msg":"Starting the OpenTelemetry Operator","opentelemetry-operator":"0.74.0","opentelemetry-collector":"ghcr.io/open-telemetry/opentelemetry-collector-releases/opentelemetry-collector:0.74.0","opentelemetry-targetallocator":"ghcr.io/open-telemetry/opentelemetry-operator/target-allocator:0.74.0","operator-opamp-bridge":"ghcr.io/open-telemetry/opentelemetry-operator/operator-opamp-bridge:0.74.0","auto-instrumentation-java":"ghcr.io/open-telemetry/opentelemetry-operator/autoinstrumentation-java:1.23.0","auto-instrumentation-nodejs":"ghcr.io/open-telemetry/opentelemetry-operator/autoinstrumentation-nodejs:0.34.0","auto-instrumentation-python":"ghcr.io/open-telemetry/opentelemetry-operator/autoinstrumentation-python:0.36b0","auto-instrumentation-dotnet":"ghcr.io/open-telemetry/opentelemetry-operator/autoinstrumentation-dotnet:0.6.0","build-date":"2023-03-29T11:22:05Z","go-version":"go1.20.2","go-arch":"arm64","go-os":"linux","labels-filter":[]}
{"level":"info","ts":"2023-04-27T11:28:16.807667255Z","logger":"setup","msg":"the env var WATCH_NAMESPACE isn't set, watching all namespaces"}
{"level":"info","ts":"2023-04-27T11:28:16.832493297Z","logger":"controller-runtime.metrics","msg":"Metrics server is starting to listen","addr":"127.0.0.1:8080"}
{"level":"info","ts":"2023-04-27T11:28:16.838661213Z","logger":"controller-runtime.builder","msg":"Registering a mutating webhook","GVK":"opentelemetry.io/v1alpha1, Kind=OpenTelemetryCollector","path":"/mutate-opentelemetry-io-v1alpha1-opentelemetrycollector"}
{"level":"info","ts":"2023-04-27T11:28:16.838714338Z","logger":"controller-runtime.webhook","msg":"Registering webhook","path":"/mutate-opentelemetry-io-v1alpha1-opentelemetrycollector"}
{"level":"info","ts":"2023-04-27T11:28:16.838741547Z","logger":"controller-runtime.builder","msg":"Registering a validating webhook","GVK":"opentelemetry.io/v1alpha1, Kind=OpenTelemetryCollector","path":"/validate-opentelemetry-io-v1alpha1-opentelemetrycollector"}
{"level":"info","ts":"2023-04-27T11:28:16.83878788Z","logger":"controller-runtime.webhook","msg":"Registering webhook","path":"/validate-opentelemetry-io-v1alpha1-opentelemetrycollector"}
{"level":"info","ts":"2023-04-27T11:28:16.838815422Z","logger":"controller-runtime.builder","msg":"Registering a mutating webhook","GVK":"opentelemetry.io/v1alpha1, Kind=Instrumentation","path":"/mutate-opentelemetry-io-v1alpha1-instrumentation"}
{"level":"info","ts":"2023-04-27T11:28:16.83883838Z","logger":"controller-runtime.webhook","msg":"Registering webhook","path":"/mutate-opentelemetry-io-v1alpha1-instrumentation"}
{"level":"info","ts":"2023-04-27T11:28:16.838853838Z","logger":"controller-runtime.builder","msg":"Registering a validating webhook","GVK":"opentelemetry.io/v1alpha1, Kind=Instrumentation","path":"/validate-opentelemetry-io-v1alpha1-instrumentation"}
{"level":"info","ts":"2023-04-27T11:28:16.838866088Z","logger":"controller-runtime.webhook","msg":"Registering webhook","path":"/validate-opentelemetry-io-v1alpha1-instrumentation"}
{"level":"info","ts":"2023-04-27T11:28:16.83896938Z","logger":"controller-runtime.webhook","msg":"Registering webhook","path":"/mutate-v1-pod"}
{"level":"info","ts":"2023-04-27T11:28:16.839004005Z","logger":"setup","msg":"starting manager"}
{"level":"info","ts":"2023-04-27T11:28:16.839308422Z","msg":"Starting server","path":"/metrics","kind":"metrics","addr":"127.0.0.1:8080"}
{"level":"info","ts":"2023-04-27T11:28:16.83936588Z","msg":"Starting server","kind":"health probe","addr":"[::]:8081"}
{"level":"info","ts":"2023-04-27T11:28:16.839088963Z","logger":"controller-runtime.webhook.webhooks","msg":"Starting webhook server"}
~~~~




## Deploy da instância do Collector

    Para fazer o deploy da instância do OpenTelemetry Collector basta executar o seguinte comando:

kubectl apply -f 02-otel-collector.yaml

    Verifique se a instalação ocorreu sem erros:

~~~~bash
kubectl get pods -n observability-backend
NAME                              READY   STATUS    RESTARTS   AGE
grafana-5bcfcc785d-lw8b5          1/1     Running   0          5h46m
loki-0                            1/1     Running   0          5h46m
mimir-0                           1/1     Running   0          5h46m
otel-collector-569977b889-ggcj4   1/1     Running   0          8m10s
tempo-7cd894b88f-tkk8j            1/1     Running   0          5h46m
~~~~



- Este trecho de código abaixo define que os Logs sejam enviados ao Loki, os Traces sejam enviados ao Tempo e as métricas sejam enviadas ao Mimir:

/home/fernando/cursos/platform-engineer-summit/dia4/OpenTelemetryCollector.yaml

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






## Deploy da Aplicação 

  - Frontend - NodeJS
  - Backend - Python
  - Backend - Java

````bash
kubectl apply -f 03-application.yaml
````

[Veja que os traces ainda não estão chegando no Grafana Tempo](http://localhost:3000/grafana/explore?orgId=1&left=%7B%22datasource%22:%22tempo%22,%22queries%22:%5B%7B%22refId%22:%22A%22,%22datasource%22:%7B%22type%22:%22tempo%22,%22uid%22:%22tempo%22%7D,%22queryType%22:%22nativeSearch%22,%22serviceName%22:%22backend2-deployment%22%7D,%7B%22refId%22:%22B%22,%22datasource%22:%7B%22type%22:%22tempo%22,%22uid%22:%22tempo%22%7D,%22queryType%22:%22traceId%22%7D%5D,%22range%22:%7B%22from%22:%22now-1h%22,%22to%22:%22now%22%7D%7D
)

## Aplicar o CR de Instrumentation:
````bash
kubectl apply -f 04-instrumentation.yaml
````

- Verifique se o CR foi criado com sucesso `kubectl get otelinst -n tutorial-application`:
````bash
NAME                 AGE     ENDPOINT                                                             SAMPLER                    SAMPLER ARG
my-instrumentation   5h38m   http://otel-collector.observability-backend.svc.cluster.local:4317   parentbased_traceidratio   1
````

## Patch do Frontend:
- Para finalizar a auto-instrumentação precisamos fazer o patch do frontend:
````batch
kubectl patch deployment frontend-deployment -n tutorial-application -p '{"spec": {"template":{"metadata":{"annotations":{"instrumentation.opentelemetry.io/inject-sdk":"true"}}}} }'
````

## Após o Patch realizado vamos fazer o rollout das apps: 
````bash
kubectl rollout restart deployment -n tutorial-application -l app=backend1
kubectl rollout restart deployment -n tutorial-application -l app=backend2
kubectl rollout restart deployment -n tutorial-application -l app=frontend

````

[Veja que os traces AGORA estão chegando no Grafana Tempo](http://localhost:3000/grafana/explore?orgId=1&left=%7B%22datasource%22:%22tempo%22,%22queries%22:%5B%7B%22refId%22:%22A%22,%22datasource%22:%7B%22type%22:%22tempo%22,%22uid%22:%22tempo%22%7D,%22queryType%22:%22nativeSearch%22,%22serviceName%22:%22backend2-deployment%22%7D,%7B%22refId%22:%22B%22,%22datasource%22:%7B%22type%22:%22tempo%22,%22uid%22:%22tempo%22%7D,%22queryType%22:%22traceId%22%7D%5D,%22range%22:%7B%22from%22:%22now-1h%22,%22to%22:%22now%22%7D%7D
)






Após finalizar a auto-instrumentação e fazer o patch do frontend:
Ao fazer describe do Pod do NodeJS, é possível verificar que o OpenTelemetry adicionou variáveis iniciadas por OT....
 

Após finalizar a auto-instrumentação e fazer o patch do frontend:
E agora tá batendo no Grafana Tempo os Traces
 



