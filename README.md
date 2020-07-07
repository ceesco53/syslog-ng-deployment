# syslog-ng-deployment

k8s deployment for syslog-ng in k8s.  Tested in kind.

Steps to create cluster and tail syslog server for messages:

git clone https://github.com/ceesco53/syslog-ns-deployment.git

cd syslog-ns-deployment

kind create cluster

kubectl create -f syslog-ns-deployment.yaml

kubectl get pods --namespace syslog-ng

kubectl get services --namespace syslog-ng

kubectl --namespace syslog-ng exec --stdin --tty <syslog-ng-deployment-pod-name> -- tail -f /var/log/messages
