# Simple Rails Application

This is a simple application ready to be deployed on [anynines](paas.anynines.com). It can create, delete and display posts. It is just a proof of concept and serves to demonstrate the deployment process on the anynines platform as a service.

## Dependencies

* Postgresql Server

## Branches

* master : This branch uses ruby mri 2.2.2 and rails 3.2.20

## Deployment

### Clone the sources:

```
git clone https://github.com/anynines/simple_rails_app.git
cd simple_rails_app
```
### anynines deployment

````
cf api https://api.aws.ie.a9s.eu
cf login
```
Use your username and password from paas.anynines.com.

```
cp manifest.yml.example manifest.yml
vim manifest.yml
```
Replace all occurences of *your_app_name* with your desired app name. You can also replace the name of the service instance *my_first_postgresql* with your desired name.

Create a PostgreSQL service instance with the free plan
```
cf create-service a9s-postgresql postgresql-single-small <postgres_service_name>
```
Make sure that the name you use for the instance matches the one in the manifest.

```
cf push
```
Visit your application url http://your_app_name.aws.ie.a9sapp.eu .
