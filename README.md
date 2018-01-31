 # Plutus prototype Docker 

This repository contains docker files used to build docker image for Plutus prototype.

The purpose of this docker image is to provide a way to setup environment ready to use for practicing Plutus programming.

You can review Plutus source code : [Plutus prototype source]

Plutus presentation and tutorial : [Plutus instruction]


### Requirements

  Only Docker is required to build and run the Cardano full node.
  
  To install Docker follow those instructions :  [Install Docker].
  
### How to build Docker image

First you need to build docker image from a docker file, docker file contains all instructions to download projects sources, dependencies and then builds the project binaries. 
Build of docker image takes some time, be patient ...

The docker image used to host cardano node is Ubuntu 16.04.

```sh
$ cd .../path/to/plutus_docker/
$ docker build - < DOCKERFILE
...
Successfully built b62ace9d8b81

$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED              SIZE
<none>              <none>              b62ace9d8b81        About a minute ago   3.96GB
````

As indicated above typing the 'docker images' command will give you the image id, in this example : b62ace9d8b81

### How to run container and interact with Plutus 
#### Start container 
To start docker container and run Plutus run the following command. Successful run should return you the id of the container.
```sh
$  docker run --name plutus -it b62ace9d8b81 /bin/bash
plutus@e9464fafb645:~/plutus-proto$
````

### Run Plutus

To be able to run Plutus interpreter you need first to run REPL with Stack, type the command 'stack repl'.
```sh
plutus@e9464fafb645:~/plutus-proto$ stack repl
Configuring GHCi with the following packages: plutus-prototype
GHCi, version 8.0.2: http://www.haskell.org/ghc/  :? for help
[ 1 of 33] Compiling Utils.Vars       ( /home/plutus/plutus-proto/src/Utils/Vars.hs, interpreted )
...
[33 of 33] Compiling Interface.REPL   ( /home/plutus/plutus-proto/src/Interface/REPL.hs, interpreted )
Ok, modules loaded: Elaboration.Contexts, Elaboration.ElabState, Elaboration.Elaboration, Elaboration.Elaborator, Elaboration.Judgments, Interface.Integration, Interface.JSVM, Interface.Prelude, Interface.REPL, Paths_plutus_prototype, Plutus.Parser, Plutus.Program, Plutus.Term, PlutusCore.BuiltinEvaluation, PlutusCore.CKMachine, PlutusCore.Evaluation, PlutusCore.EvaluatorTypes, PlutusCore.PatternMatching, PlutusCore.Program, PlutusCore.Term, PlutusTypes.ConSig, PlutusTypes.Type, Utils.ABT, Utils.Elaborator, Utils.Env, Utils.Eval, Utils.JSABT, Utils.Names, Utils.Pretty, Utils.ProofDeveloper, Utils.SuffixParser, Utils.Unifier, Utils.Vars.
Loaded GHCi configuration from /tmp/ghci15/ghci-script
*Utils.Vars Elaboration.Contexts Elaboration.ElabState Elaboration.Elaboration Elaboration.Elaborator Elaboration.Judgments Interface.Integration Interface.JSVM Interface.Prelude Interface.REPL Plutus.Parser Plutus.Program Plutus.Term PlutusCore.BuiltinEvaluation PlutusCore.CKMachine PlutusCore.Evaluation PlutusCore.EvaluatorTypes PlutusCore.PatternMatching PlutusCore.Program PlutusCore.Term PlutusTypes.ConSig PlutusTypes.Type Utils.ABT Utils.Elaborator Utils.Env Utils.Eval Utils.JSABT Utils.Names Utils.Pretty Utils.ProofDeveloper Utils.SuffixParser Utils.Unifier Utils.Vars>
````
And load the Plutus demo.
```sh
... Utils.Vars> replFile "src/Demo.pls"
$> 
```
You are know in the Plutus command line interface and can start writing you first contract.

Enjoy !


**Emurgo Vietnam - 2018**

   [Install Docker]: <https://docs.docker.com/engine/installation/>
   [Plutus prototype source]: <https://github.com/input-output-hk/plutus-prototype>
   [Plutus instruction]: <https://cardanodocs.com/technical/plutus/introduction/>


