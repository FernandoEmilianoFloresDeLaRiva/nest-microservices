## Try this project on a dev environment

1. Clone this repository
2. Create an .env based on the .env.template
3. Run the command `git submodule update --init --recursive` to start the submodules
4. Run the command `docker compose up --build`

# Prod

1. Clone this repositorio
2. Create an .env based on the .env.template
3. Run the command `docker compose -f docker-compose.prod.yml build`

## If you want to try with kubernetes

1.  Go to the directory store-ms
2.  Run the command `helm create <name>`
3.  Create your own secrets based on this contexts:
```yml
- secretKeyRef:
    name: auth-secrets
    key: DATABASE_URL
- secretKeyRef:
    name: auth-secrets-2
    key: JWT_SECRET
- secretKeyRef:
    name: orders-secrets
    key: ORDERS_DATABASE_URL
- secretKeyRef:
    name: payments-secrets
    key: stripe_secret
- secretKeyRef:
    name: payments-secrets
    key: endpoint_secret
```
+ To create one secret at a time, use the following command`kubectl create secret generic <nombre> --from-literal=key=value`
+ To create many secrets at once, use the following command`kubectl create secret generic secret1 --from-literal=key1=value1 --from-literal=key2=value2`
4.  Run the command to get all the updates `helm upgrade store-ms .`
