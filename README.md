There is a need for 2 Kube secrets:
```
loomio:
  DATABASE_URL: postgresql://postgres:passwordgoeshere@loomio-db/loomio_mayara
  DEVISE_SECRET: 'uniquehash'
  SECRET_COOKIE_TOKEN: 'uniquehash'
loomio-db:
  POSTGRES_PASSWORD: passwordgoeshere
```
Those secrets are read as environment variables as per the deployment template

There is a flag to enable db initialisation in `values.yaml`. It must be set to true, `helm install` then set it to false and `helm upgrade`
