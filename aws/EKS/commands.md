#To start an eks cluster using eksctl tool

eksctl create cluster --name=<cluster-name> --nodes=3 --node-ami=auto --region=${AWS_REGION}

#To shutdown an eks cluster

eksctl delete cluster --name=<cluster-name>
