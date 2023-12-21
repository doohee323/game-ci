# Unity-CI image of the Unity Editor

#### `unity-ci/editor`

Dockerised Unity Editor made for continuous integration.

## Usage

Run the editor image using an interactive shell

```bash
docker run -it --rm unityci/editor:[tag] bash
```
example

```bash
docker run -it --rm unityci/editor:ubuntu-2020.1.1f1-android-0.3.0 bash
```


Run the editor 

```bash
unity-editor help
```

## License

[MIT license](https://github.com/game-ci/docker/blob/main/LICENSE)

cd /Volumes/data1/game-ci
SNAPSHOT_IMG=devops-unity_base
docker image build . -f editor/Dockerfile #--no-cache

SNAPSHOT_IMG=unityci_hub
docker buildx build --platform linux/arm/v7 -t ${SNAPSHOT_IMG} -f base/Dockerfile .

