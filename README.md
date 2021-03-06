# Docker Image GitLab CI Build Environment
Docker Image CI Build Environment for GitLab Runner.

[Docker Image](https://hub.docker.com/r/graybullet/dockerbuildenv/)

Important: Remove android sdk. If you required Android SDK, you must install by GitLab Runner's setup script.

Important: Remove OpenJDK 8u131.


## Environment
* Apache Ant and Gradle
* Chromium and chromedriver (It starts with headless by default)
* GitLab Runner
* zip and unzip command
* nkf
* nvm ([preinstall Node.js](node_versions.list))
* rbenv ([preinstall Ruby](ruby_versions.list))
* OpenJDK 8 ([preinstall Java](java_versions.list))
* ~~Android SDK~~
  - ~~build-tools (25.0.0, 24.0.3, 23.0.3, 22.0.1, 21.1.2)~~
  - ~~tools, platform-tools, platform~~


## Using
```
$ docker pull graybullet/dockerbuildenv
$ docker run -it graybullet/dockerbuildenv /bin/bash
```


### GitLab Runner
If you use the GitLab Runner, write `source /etc/gitlab-runner.conf` to your `.gitlab-ci.yml`.

```yml
before_script:
  - source /etc/gitlab-runner.conf
  - bundle install --path vendor/bundle
  - npm install --no-progress
```

