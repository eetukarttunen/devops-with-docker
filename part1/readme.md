## Exercise 1.1: Getting started
~~~
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                      PORTS     NAMES
9dca673cf5bb   nginx     "/docker-entrypoint.…"   About a minute ago   Exited (0) 18 seconds ago             boring_einstein
65f34b02042a   nginx     "/docker-entrypoint.…"   About a minute ago   Exited (0) 9 seconds ago              jolly_leavitt
372ac1337833   nginx     "/docker-entrypoint.…"   About a minute ago   Up About a minute           80/tcp    cranky_keller
~~~
## Exercise 1.2: Cleanup
~~~
>docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

>docker images
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE
~~~

## Exercise 1.3: Secret message
~~~
>docker run -d -it --name part1.3 devopsdockeruh/simple-web-service:ubuntu
Unable to find image 'devopsdockeruh/simple-web-service:ubuntu' locally
ubuntu: Pulling from devopsdockeruh/simple-web-service
5d3b2c2d21bb: Pull complete
3fc2062ea667: Pull complete
75adf526d75b: Pull complete
965d4bbb586a: Pull complete
4f4fb700ef54: Pull complete
Digest: sha256:d44e1dce398732e18c7c2bad9416a072f719af33498302b02929d4c112e88d2a
Status: Downloaded newer image for devopsdockeruh/simple-web-service:ubuntu
f000424699d6e4d3c18887cac797c12251f27ea210c14c351b3895c9e888c397

>docker exec -it part1.3 bash
root@f000424699d6:/usr/src/app# tail -f ./text.log
2022-05-13 19:55:48 +0000 UTC
2022-05-13 19:55:50 +0000 UTC
2022-05-13 19:55:52 +0000 UTC
2022-05-13 19:55:54 +0000 UTC
2022-05-13 19:55:56 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
2022-05-13 19:55:58 +0000 UTC
2022-05-13 19:56:00 +0000 UTC
2022-05-13 19:56:02 +0000 UTC
2022-05-13 19:56:04 +0000 UTC
2022-05-13 19:56:06 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
~~~

## Exercise 1.4: Missing dependencies
In this exercise it was mandatory to do apt-get update first. Commands:
~~~
>docker run -it ubuntu
>apt-get update
>apt-get install curl
>sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'
Input website:
helsinki.fi
Searching..
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="https://www.helsinki.fi/">here</a>.</p>
</body></html>
~~~

## Exercise 1.5: Sizes of images

~~~
>docker run -d -it --name part1.5 devopsdockeruh/simple-web-service:alpine
>docker images

REPOSITORY                          TAG       IMAGE ID       CREATED         SIZE
ubuntu                              latest    d2e4e1f51132   2 weeks ago     77.8MB
devopsdockeruh/simple-web-service   ubuntu    4e3362e907d5   14 months ago   83MB
devopsdockeruh/simple-web-service   alpine    fd312adc88e0   14 months ago   15.7MB

>docker exec -it part1.5 sh
>tail -f ./text.log
2022-05-14 19:14:41 +0000 UTC
2022-05-14 19:14:43 +0000 UTC
2022-05-14 19:14:45 +0000 UTC
2022-05-14 19:14:47 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
~~~
Alpine image size was samaller and secret message was the same.

## Exercise 1.6: Hello Docker Hub
secret message: "This is the secret message"
command(s): 
~~~
>docker run -it devopsdockeruh/pull_exercise
~~~



