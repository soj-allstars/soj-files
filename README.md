# soj-files
Files related to deployment.

Currently the docker-compose.yml only work on docker-compose.

## Deploy
First of all, install docker and docker-compose.

Clone this repo, cd to the cloned directory.

Run
```
docker-compose up -d
```
to start the containers.

Run django migrations:
```
docker-compose exec soj python manage.py migrate
```

Scale the number of judger if needed:
```
docker-compose scale soj-judger=4
```
Change `4` to the number you want.

Create a django superuser:
```
docker-compose exec soj python manage.py createsuperuser
```

Run django collectstatic:
```
docker-compose exec soj python manage.py collectstatic
```

And congrats! You've successfully deploy soj to a single machine. Next step is to go to `/addproblem` to add some BRAND NEW problems!
