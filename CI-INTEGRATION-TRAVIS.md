# React Native Continuous Integration: TravisCI

### .travis.yml
```
language: android
jdk: oraclejdk8
dist: xenial
sudo: required

cache:
  yarn: true
  directories:
    - node_modules

android:
  components:
    - tools
    - platform-tools
    - build-tools-28.0.3
    - android-28

matrix:
  include:
    - name: "ESLint & Unit Test"
      env: LINT_UNIT_TEST=yes
      os: linux
    
    - name: "Build Android Release"
      env: ANDROID_BUILD=yes GRADLE_ARGS=bundleRelease
      os: linux

before_install:
  - nvm install 10
  - npm install -g yarn

install:
  - yarn install

before_script:
  - chmod +x ./android/gradlew

script:
  - if [ "$LINT_UNIT_TEST" = "yes" ]; then
      yarn lint;
      yarn test;
    fi
  - if [ "$ANDROID_BUILD" = "yes" ]; then
      cd android && ./gradlew clean $GRADLE_ARGS;
    fi
```
