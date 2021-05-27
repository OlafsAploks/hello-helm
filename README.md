# hello-helm

This is forked from the [original repository](https://github.com/open-toolchain/hello-helm) and adjust to personal needs.

Creates deployment and service and optionally an ingress resource.

## How to deploy

```
cd to /chart/hello
helm install <release-name> .
```

This will create a deployment that will pull the specified image from the specified repository.

### In case of custom image

_Repo contains parts of steps to deploy custom image as well. To do that create Docker registry and push built image to that (might create CI/CD pipeline). But default image is sufficient for current use cases of testing._

```
imagePullSecrets:
- name: {{ .Values.image.pullSecret }}
```

```
pullSecret: regsecret
```
