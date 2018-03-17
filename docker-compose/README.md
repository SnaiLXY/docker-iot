# WSO2 IoT Server and Broker with Analytics support

## Prerequisites

  * [Docker](https://www.docker.com/get-docker) and [Docker Compose](https://docs.docker.com/compose/install/#install-compose) are required to run this deployment.

## How to Run

  1. Build IoT Server, Broker and Analytics Images using [Dockerfiles](../../dockerfiles/README.md)
     > In the `docker-compose.yml`, remove the `dockerhub.wso2.com/` prefix from the `image` name
            
     > For example, change the line `image: dockerhub.wso2.com/wso2iot-server:3.2.0` to `image: wso2iot-server:3.2.0`
  2. Pull MySQL Docker image :
     ```
     docker pull mysql:5.7.20
     ```

  3. Download the latest Docker resources for the product from [releases](https://github.com/wso2/docker-iot/releases) 
     page or clone this repository <br> to your local machine and switch to latest release tag.
     
     > Note that the local copy of `docker-iot` repository will be referred to as `[docker-iot]` from this point onwards.

  4. Switch to docker-compose folder :
     ```
     cd docker-iot/docker-compose
     ```

  5. Before to start deployment process, add a host entry pointing to the Docker host machine IP address. <br>
     For an example if the Docker host is accessible via 127.0.0.1 on a Linux or Mac machine, add <br>
     following entry to /etc/hosts file :
     ```
     127.0.0.1 wso2iot-server wso2iot-analytics wso2iot-broker
     ```
     
  6. Execute following Docker Compose command to start the deployment :
     ```
     docker-compose up
     ```

  7. Access management console via a web browser :
     ```
     For Devicemgt - https://wso2iot-server:9443/devicemgt
     For App Publisher - https://wso2iot-server:9443/publisher
     ```

