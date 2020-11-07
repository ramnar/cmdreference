## Steps to do after changing the code

#To build a specific subsection in kubernetes

make WHAT=cmd/kubectl

#To run a specific testpackage

make WHAT=./staging/src/k8s.io/kubectl/pkg/cmd/delete/

#To run a single test class

make test-cmd WHAT=service_accounts ( In https://github.com/kubernetes/kubernetes/blob/master/test/cmd/core.sh, you will find function of the form run_service_accounts_tests )


## setup minikube in local linux box

https://minikube.sigs.k8s.io/docs/start/

## Testing reference

https://github.com/kubernetes/community/blob/master/contributors/devel/development.md#a-quick-start-for-testing-kubernetes
