
## Install Tekton

See https://github.com/tektoncd/pipeline/blob/master/docs/install.md

   kubectl apply --filename https://storage.googleapis.com/tekton-releases/pipeline/latest/release.yaml

## Install Tekton tasks

   kubectl apply -f https://raw.githubusercontent.com/tektoncd/catalog/v1beta1/git/git-clone.yaml

## Allow use of multiple PVCs

   kubectl patch cm feature-flags -n tekton-pipelines --patch '{"data":{"disable-affinity-assistant": "true"}}'

## Docker credentials

   kubectl create secret docker-registry dockercreds --docker-server=https://index.docker.io/v1/ --docker-username=<DOCKERHUB_USERNAME> --docker-password=<DOCKERHUB_PASSWORD> --docker-email <DOCKERHUB_EMAIL>


