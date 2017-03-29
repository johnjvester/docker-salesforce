## johnjvester/docker-salesforce

> The docker-salesforce image is based upon the amkor/docker-salesforce image (created by Adam Crump), 
> without referencing the salesforce.jar file and adding support for CURL (for Slack integration).
>
> The image is designed to be as lean as possible, leveraging Apline and the following components:
> - bash
> - openjdk8
> - apache-ant
> - curl  

### Getting Started

The image is designed to work with pipeline build processes, but could be used independantly using the following docker command:

`docker pull johnjvester/docker-salesforce`

#### Example - using with BitBucket Pipelines

Below, is a simple bitbucket-pipelines.yml configuration:

```
# ----- 
image: johnjvester/docker-salesforce

pipelines:
  default:
    - step:
        script:
          - echo "Running Default Script and hitting DZone.com web-page"
          - ant -buildfile build/build.xml deploy 
          - curl 'https://dzone.com'
```

The codebase itself would include a /build folder, which would house the ant-salesforce.jar file, build.properties and build.xml files.  

Created by [John Vester](https://www.linkedin.com/in/johnjvester), because I truly enjoy writing code.
