# Deploying Backing Services

## General (for all services)

- Create the `namespace` from `kubectl apply -f ./src/namespace.yaml`

## Microsoft SQL Server

- Choose a strong password
- Base64 it!
- Change the `SA_PASSWORD` value in `./src/mssql/secret.yaml` with the base64 encoded password
- Create a `Secret` object with `kubectl apply -f ./src/mssql/secret.yaml`
- Create a `Volume Clain` object with `kubectl apply -f ./src/mssql/storage.yaml`
- Create the server `Deployment` and related `Service` with `kubectl apply -f ./src/mssql/deployment.yaml`

This recipe expose SQL Server in default port. Look into Service external IP to get the address that SQL Server will listen.
