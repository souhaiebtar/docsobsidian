

```yaml
image: eclipse-temurin:17-jdk

  

variables:

  GRADLE_OPTS: "-Dorg.gradle.daemon=false"

  

stages:

  - build

  - test

  - package

  - release

  

before_script:

  - export GRADLE_USER_HOME=`pwd`/.gradle

  

cache:

  paths:

    - .gradle/wrapper

    - .gradle/caches

  

build:

  stage: build

  script:

    - ./gradlew assemble

  artifacts:

    paths:

      - build/libs/*.jar

  

test:

  stage: test

  script:

    - ./gradlew test

  

package:

  stage: package

  script:

    - ./gradlew bootJar

  artifacts:

    paths:

      - build/libs/*.jar

  

release:

  stage: release

  script:

    - echo "Creating release with .jar file"

  artifacts:

    paths:

      - build/libs/*.jar

  release:

    tag_name: 'v$CI_PIPELINE_IID'

    description: 'Release v$CI_PIPELINE_IID'

  only:

    - main
```