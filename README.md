kind create cluster --name airflow-cluster --config kind-cluster.yaml



kubectl cluster-info
kubectl get nodes -o wide



kubectl create namespace airflow
kubectl get namespaces


helm repo add apache-airflow https://airflow.apache.org
helm repo update
helm search repo airflow
helm install airflow apache-airflow/airflow --namespace airflow --debug


kubectl get pods -n airflow


helm ls -n airflow





kubectl port-forward svc/airflow-webserver 8080:8080 -n airflow --context kind-airflow-cluster



helm show values apache-airflow/airflow > values.yaml


helm upgrade --install airflow apache-airflow/airflow -n airflow -f values.yaml --debug
helm ls -n airflow 


kubectl exec <webserver_pod_id> -n airflow -- airflow providers list

