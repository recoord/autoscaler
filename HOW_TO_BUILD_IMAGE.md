    cd cluster-autoscaler

Create CA binary:

    make build-in-docker

Build new CA image

    docker build -t autoscaler:v1.18.3-2 -f Dockerfile .

- **v1.18.3-2**  is tag, update it to fit versioning.

Push image to ECR:

    docker tag autoscaler:v1.18.3-2 454099695756.dkr.ecr.eu-west-1.amazonaws.com/cluster-autoscaler:v1.18.3-2
    docker push 454099695756.dkr.ecr.eu-west-1.amazonaws.com/autoscaler:v1.18.3-2
