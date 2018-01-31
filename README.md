 # Plutus prototype Docker 

This repository contains docker files used to build docker image of Plutus prototype.
The purpose of this docker image is to provide a way to set up environement ready to use for practice Plutus programming.
You can review Plutus source code : [Plutus prototype source]
Plutus presentation and tutorial : [Plutus instruction]


### Requirements

  Only Docker is required to build and run the Cardano full node.
  To install Docker follow those instructions :  [Install Docker].
  
### How to build Docker image

First you need to build docker image from a docker file, docker file contains all instructions to download projects sources, dependencies and then builds the project binaries. Build of docker image takes some time, be patient ...
The docker image used to host cardano node is Ubuntu 16.04.

```sh
$ cd ./plutus-proto
$ docker build - < DOCKERFILE
````



**Emurgo Vietnam - 2018**

   [Install Docker]: <https://docs.docker.com/engine/installation/>
   [Plutus prototype source]: <https://github.com/input-output-hk/plutus-prototype>
   [Plutus instruction]: <https://cardanodocs.com/technical/plutus/introduction/>


