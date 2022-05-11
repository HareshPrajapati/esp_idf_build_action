# esp_idf_build_action


GitHub Action for ESP32 CI

## Usage

Workflow definition

```
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout repo
      uses: actions/checkout@v3
      with:
        submodules: 'recursive'
    - name: Espressif (ESP-IDF) Build Action
      uses: HareshPrajapati/esp_idf_build_action@V2
      with:
        esp_idf_version: 'latest'
        target: esp32
        path: 'examples/project'
```

## Parameters

### `path`

Path to the project to be built

### `esp_idf_version`

The version of ESP-IDF for the action. Default value `latest`.

It must be one of the tags from [Docker Hub](https://hub.docker.com/r/espressif/idf/tags)

More information about supported [versions of ESP-IDF](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/versions.html#support-periods)

### `target`

Type of ESP32 to build for. Default value `esp32`.

The value must be one of the supported ESP-IDF targets as documented [here](https://github.com/espressif/esp-idf#esp-idf-release-and-soc-compatibility)

### `command`

Optional: Specify the command that will run as part of this GitHub build step.

Default: `idf.py build`
