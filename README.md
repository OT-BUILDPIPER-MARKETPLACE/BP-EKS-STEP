# BP-EKS-STEP
I'll setup EKS


## Setup
* Clone the code available at [BP-TF-STEP](https://github.com/OT-BUILDPIPER-MARKETPLACE/BP-EKS-STEP)
* Build the docker image

```
git submodule init
git submodule update
docker build -t ot/tf-eks-step:1.1.0 .
```

* Do local testing via image only

```
# terraform with default(apply)
docker run -it --rm -v $PWD:/src -e WORKSPACE=/src -e CODEBASE_DIR=/ ot/tf-eks-step:1.1.0

# terraform with plan
docker run -it --rm -v $PWD:/src -e WORKSPACE=/ -e CODEBASE_DIR=/src -e TF_CODE_LOCATION=<?> -e AWS_ACCESS_KEY_ID=<?> -e AWS_SECRET_ACCESS_KEY=<?> -e INSTRUCTION=plan ot/tf-elasticache-step:0.1

```