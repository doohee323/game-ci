# GameCI base image for Unity images

#### `unity-ci/base`

Base image used to produce hub and editor images.

Not indended for external use per se.

## License

[MIT license](https://github.com/Unity-CI/docker/blob/main/LICENSE)

cd /Volumes/data1/game-ci
SNAPSHOT_IMG=devops-unity_base
docker image build . -f base/Dockerfile #--no-cache

SNAPSHOT_IMG=unityci_base
docker buildx build --platform linux/arm/v7 -t ${SNAPSHOT_IMG} -f base/Dockerfile .

TAG=t1
DOCKER_ID=docker.mirrorcity.io
docker login ${DOCKER_ID}
docker tag ${SNAPSHOT_IMG}:latest ${DOCKER_ID}/${SNAPSHOT_IMG}:${TAG}
docker push ${DOCKER_ID}/${SNAPSHOT_IMG}:${TAG}



