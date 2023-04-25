

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