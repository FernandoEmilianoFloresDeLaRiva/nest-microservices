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
1. Go to the directory store-ms
2. Run the command `helm install store-ms .`
3. Run the command to get the updates `helm upgrade store-ms .`