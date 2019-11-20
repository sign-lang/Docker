# Sign - Docker

[Docker images][1]

[1]: https://hub.docker.com/u/signlang

## Base images

These images have everything needed for Sign development

```
make -C base all
make -C base <image>
```

###### Options

- `PUSH=1` to upload the image to dockerhub
- `DEBUG=1` to see the docker build output
- `SHELL='sh -x'` to see the commands getting executed
