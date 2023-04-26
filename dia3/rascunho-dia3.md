

git status
git add .
git commit -m "DIA 3 - PLATFORM ENGINEER SUMMIT 2023"
eval $(ssh-agent -s)
ssh-add /home/fernando/.ssh/chave-debian10-github
git push
git status



## DIA 3 - PLATFORM ENGINEER SUMMIT 2023

19:00 - 19:45
Alice Paixão - Internal Developer Platform: Transformar a experiência do dev e impulsionar a velocidade de entrega

20:00 - 20:45
Mateus Prado - It's all about Product Engineering

21:00 - 21:45
Pery Lemke - Developer Effectiveness - Como melhorar a nossa eficácia?

22:00 - 22:45
Camilla Martins - Trabalhando no exterior com infraestrutura









# Alice Paixão - Internal Developer Platform: Transformar a experiência do dev e impulsionar a velocidade de entrega

- Usuários que terão os acessos.




## Componentes que a plataforma precisa ter?

- Gerenciamento de configuração de aplições e serviços.
- Automação de Infraestrutura(IAC).
- Deploy por ambientes.
- Gerenciamento de Implantações(CI/CD)
- Controle de acesso(Principio do menor privilégio)



## Day0/Day1/Day2

Day0/Day1/Day2

se preparar e fazer pequenas entregas

- Primeiro dia, day0
tirar o dia para treinar o time sobre IAC, supondo que o time não entenda de IAC.

- Segundo dia, day1
alinhamentos com os times de Dev's

- Terceiro dia, day2
Implantar primeira parte






## O que foi feito?

- Clusters manuais > IAC > Terraform

- Alterar serviços de maneira segura, sem necessidade de edição manual > GitOps > ArgoCD





## Portal

- Pode ser importante o acompanhamento de um DEV-Frontend nesta missão.







## Compartilhando resultados

- Curva de aprendizado.

- 4 métricas
Deployment Frequency
Lead time for Changes
Change Failure Rate
Time to Restore Service





- Camadas para Plataforma
de forma self-service, o próprio Dev poder ajustar um parametro de RAM, CPU, replicas, etc

- Feedback dos times
satisfação dos clientes(Dev's)



## ACESSOS

- Acessos bem selecionados, garantem economias, pois o usuário só vai ter acesso a recursos que precisa de fato.
- Cluster



## IMPORTANTE
- Cuidar para que UX seja amigável.
experiencia do usuário pode ditar o sucesso ou fracasso da implantação do IDP











# Mateus Prado - It's all about Product Engineering

No final das contas a pergunta é: "QUAL PROBLEMA QUEREMOS RESOLVER?"

## THE DEFINITIONS TEAMS

- Envolver os times que vão ditar os requisitos da plataforma
usuários que vão poder contribuir de verdade na modelagem da plataforma


- Saber responder:
O que?
Como?

- Saber explicar o problema que queremos resolver.