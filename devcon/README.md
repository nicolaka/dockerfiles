## Devcon: a Sample Development Environment in a Container

This is a sample development container that I use with Docker for Mac. Feel free to use it as your dev environment! How to use:

```
$docker run -it --rm --hostname devcon -v /var/run/docker.sock:/var/run/docker.sock nicolaka/devcon:latest
```

Optionally, you can moutn your local dev directory inside the container by adding `-v /path/to/dir:/root`

Enjoy!
 

