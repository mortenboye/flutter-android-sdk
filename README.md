## Bitbucket Pipelines

This image can be used to test and build Android APKs developed with Flutter. Here is an example `bitbucket-pipelines.yml` for Bitbucket Pipelines including caches for gradle and gradlewrapper:

```
image: mortenboye/flutter-android-sdk

pipelines:
  default:
    - step:
        caches:
          - gradle
          - gradlewrapper
        script:
          - echo "Building APK..."
          - flutter doctor
          - flutter -v build apk

definitions:
  caches:
    gradlewrapper: ~/.gradle/wrapper
```
