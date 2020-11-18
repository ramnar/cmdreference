# Steps to do after changing the code

## To build a specific subsection of code in kubernetes(relative to root directory)

make WHAT=cmd/kubectl

## To run unit test on a single package(relative to root directory)

make test WHAT=./staging/src/k8s.io/kubectl/pkg/cmd/create GOFLAGS="-v"


## To run a single test class

make test-cmd WHAT=service_accounts ( In https://github.com/kubernetes/kubernetes/blob/master/test/cmd/core.sh, you will find function of the form run_service_accounts_tests )



## To run single integration test 

TestServiceAccountAutoCreate with the verbose flag set.

make test-integration WHAT=./test/integration/serviceaccount GOFLAGS="-v" KUBE_TEST_ARGS="-run ^TestServiceAccountAutoCreate$"

## To run single e2e test


# References
## setup minikube in local linux box

https://minikube.sigs.k8s.io/docs/start/

## Testing reference

https://github.com/kubernetes/community/blob/master/contributors/devel/development.md#a-quick-start-for-testing-kubernetes
