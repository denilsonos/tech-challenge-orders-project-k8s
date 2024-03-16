# tech-challenge-orders-project
Projeto fase 3



## Deploy

Para rodar o projeto você precisa configurar o arquivo .env, utilizando como base o .env.example.

Execute o comando abaixo para criar o arquivo de secrets com base no .env

```bash
kubectl create secret generic app-secret --from-env-file=/.env
```

Feito isso, basta aplicar os arquivos do k8s.

```bash
kubectl apply -f kubernetes/config-map-app.yaml
kubectl apply -f kubernetes/deployment-app.yaml
kubectl apply -f kubernetes/hpa.yaml
kubectl apply -f kubernetes/service-app.yaml
kubectl apply -f kubernetes/load-balancer.yaml
```

Depois de aplicar os arquivos execute para visualizar a URL de acesso ao load balancer
```bash
kubectl get svc
```