This is a dockerized version of django channels example app:

https://github.com/jacobian/channels-example


All credits for writing the app go to @jacobian.


## Running with `docker-compose`


### Just the demo

If you just want to try the demo out, all you need to do is to clone this repository and run:

```
$ docker-compose up
```


### Also changing the app

If you would like to play with the app itself, you should clone it locally:

```
$ git clone https://github.com/jacobian/channels-example
```

and then mount the sources inside containers. There's a special compose file for this use case:

```
$ docker-compose -f docker-compose-with-mount.yml up
```

Django is able to reload its webserver if you change the code, that's why sources are mounted inside.


## Open in browser

You can open browser now and check the app:

```
xdg-open http://$(docker inspect --format '{{ .NetworkSettings.IPAddress }}' $(docker-compose ps -q web)):8000
```
