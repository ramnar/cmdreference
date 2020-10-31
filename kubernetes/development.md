#To build a specific subsection in kubernetes

make WHAT=cmd/kubectl

#To run a specific test

make WHAT=./staging/src/k8s.io/kubectl/pkg/cmd/delete/
