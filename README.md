This is a dockerized version of django channels example app:

https://github.com/jacobian/channels-example


All credits for writing the app go to @jacobian.


## Running with `docker-compose`


### Prereq

Django is able to reload webserver if we change code, let's take advantage of that! All we have to do is to mount sources inside container(s). That means that we have to clone the sources locally:

```
$ git clone https://github.com/jacobian/channels-example
```

Now we can bring the application to life:

```
$ docker-compose up
```

The only thing to do is to populate database:

```
$ docker exec -ti openhouse2016demo_web_1 python /opt/app/channels-example/manage.py migrate
```

You can open browser now and check the app:

```
xdg-open http://$(docker inspect --format '{{ .NetworkSettings.IPAddress }}' $(docker-compose ps -q web)):8000
```
