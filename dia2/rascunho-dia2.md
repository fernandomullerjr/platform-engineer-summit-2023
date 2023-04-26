

git status
git add .
git commit -m "DIA 2 - PLATFORM ENGINEER SUMMIT 2023"
eval $(ssh-agent -s)
ssh-add /home/fernando/.ssh/chave-debian10-github
git push
git status



##  DIA 2 - PLATFORM ENGINEER SUMMIT 2023

19:00 - 19:45
Henrique Oliveira e Rodrigo Guilherme Santos Silva - From Days to Minutes

20:00 - 20:45
Leandro Proença - Construindo uma pipeline de entrega contínua com Tekton

21:00 - 21:45
Sergio Soares - CDK8s, uma forma diferente de escrever seus Charts

22:00 - 22:45
Roze Anne Cardoso - Se devops é cultura, pq só falamos de ferramentas?! Devops em uma visão de negócio










19:00 - 19:45
Henrique Oliveira e Rodrigo Guilherme Santos Silva - From Days to Minutes



- Melhorar a experiência do developer.
DX(Developer Experience)


- GitOps
Iniciaram utilizando
atlantis + terraform


- Controlar custos mesmo com o IDP.


- Sintaxe simples.

- Abstrair parametros e complexidade.

- Evitar configuração excessiva de parametros.
ex:
ele não precisa saber de OIDC, etc

- Ser open source

- Integração com Kubernetes, ArgoCD, GitOps Flow
usam GitHub Actions com GitOps



- Crossplane é a fonte de verdade para toda a aplicação!





## Scaffolding 

- É o ato de fornecer um Template que vai alimentar o Backstage.

### Introduction

This tutorial will show you how to create a basic scaffolder template in Backstage.

You can find detailed docs on writing scaffolder templates here.

The Roadie Backstage scaffolder is a feature that allows you to define software templates to create new software projects, update existing ones or simply perform repeated tasks in a consistent manner.

Scaffolder templates are defined in YAML files and loaded into the Backstage catalog in the same way that other entities are loaded into Backstage. A template contains one or more steps which run sequentially during execution.

A Scaffolder template is then run on demand by the users of Backstage to execute the software template.


https://roadie.io/docs/getting-started/scaffolding-components/
<https://roadie.io/docs/getting-started/scaffolding-components/>


https://backstage.io/docs/reference/plugin-scaffolder/
<https://backstage.io/docs/reference/plugin-scaffolder/>










## Crossplane

- O Crossplane é muito importante, ele facilita muita coisa.
- O Crossplane é muito importante, ele facilita muita coisa.
- O Crossplane é muito importante, ele facilita muita coisa.
- O Crossplane é muito importante, ele facilita muita coisa.











## Backstage

- É importante ter 1 arquiteto que entenda de NodeJS, para auxiliar na criação de Templates, Plugins, etc, para o Backstage.


No ArgoCD o Backstage cria 2 aplicações
1 é a aplicação em si
1 é a infra da aplicação
Isto permite ter um maior controle sobre o que queremos salvar, modificar ou matar, por exemplo.
 Isto ajuda a garantir também que a aplicação só vai subir, depois que a infra subir.





Backstage já cria a documentação
 



Serviços que são oferecidos
 

São adicionados mais serviços, conforme são desenvolvidos e amadurecidos.


 

Essa tela “Task Activity” é o Scaffold, vai trazer os detalhes do que está sendo implantado.
Catalogo 




O uso do Crossplane dispensa o uso do Vault, pois já injeta as variáveis secretas no Kubernetes.





















20:00 - 20:45
Leandro Proença - Construindo uma pipeline de entrega contínua com Tekton




O CircleCI utiliza Webhooks para se falar com o repositório Git.


Ideal é empacotar




Tem 3 pods, 1 da task antiga, 2 da Pipeline que tem 2 tasks.




Tekton CLI
 


 
Como é utilizado o TaskRef, ele puxa da task que foi instalada via Tekton Hub.





PipelineRun é a ponta final.
Ele vai passar parâmetros.

Tasks não compartilham dados por default.



 




 



 




O workspace “shared-data” é passado com o nome “output”, aonde está a seta amarela.



  


 



 


 

TriggerBinding, envia os parâmetros ao TriggerTemplate.
TriggerBinding, envia os parâmetros ao TriggerTemplate.

TriggerBinding, envia os parâmetros ao TriggerTemplate.

O TriggerBinding busca os dados com base no Webhook.
O TriggerBinding busca os dados com base no Webhook.

O TriggerBinding busca os dados com base no Webhook.




 
 