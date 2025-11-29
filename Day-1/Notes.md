Controle Plane NODE - Controla o Cluster
Workers NODE - Nos que tem as aplicacoes rodando

## ARQUITETURA CONTROL PLANE:
- ETCD = Storage
- Kube API Server = Cerebro do cluster, gerencia o scheduler e o controller e envia as infos para o etcd.
- Kube Scheduler = agendador, gerenciamento de onde rodas os containers
- Kube Controller Manager = Controlador


## ARQUITETURA WOKERS NODE:
- Kubelet = Agent dos nós dos containers, em cada node tem um.
- Kubeproxy = Faz a comunicacao dos nodes com o mundo externo, redes

## PORTAS
- ETCD = 2379, 2380 -> TCP
- Kube API Server = 6443 -> TCP
- Kubelet = 10250 -> TCP
- Kube Scheduler = 10251 -> TCP
- Kube Controller Manager = 10252 -> TCP
- Kubeproxy = 
- NodePort = 30000 - 32767 -> TCP - Pega as portas e seta na 80
- Weave Net = 6783 TCP, 6784 UDP

Pods = menor unidade do cluster onde fica a app
Deployment = Responsável por garantir as configs dos pods, aqui podemos definir as replicas, quantidade de memoria, imagem, etc.
Replica Set = Garantir a quantidade das replicas do deployment
Service = Reponsavel por fazer que os pods sejam acessiveis fora do Node. Podemos definir uma porta para o Node tipo a 3001 e acessar 
externamente no navegador digitando http://node:3001

KIND = Kubernetes in DOCKER

COMANDOS KUBECTL
Quer pegar informacoes dos objetos uitilize:
kubectl get + nome do objeto -> kubectl get node -> services -> deployment
Para acessar os pods primeiro devemos listar as namespaces: kubectl get namespaces
Dentro do kube-system ficam os pods: kubectl get pods -n kube-system
Comando para trazer o IP e o NODE: kubectl get pods -n kube-system -o wide
Se utlizar o -A no final ele pega as infos de todos os clusters.
kubectl get services - A

Acessar o pod: kubectl exec -ti nomepode -- bash
obs: se o pod tiver mais de um container passar o nome do container depois do nome do pod

configurar para facilitar os comandos acesse: vim /root/.bash_profile
Dentro do VIM configure:
source /root/.kube/completion.bash.inc
alias k=kubectl








