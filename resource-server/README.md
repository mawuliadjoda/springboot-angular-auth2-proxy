./mvnw package
docker build -t resource-server .
docker tag resource-server:latest adjodamawuli/resource-server:latest
docker push adjodamawuli/resource-server:latest


helm delete resource-server
helm install resource-server ./charts/resource-server


Here is the complete sequence of commands you would typically run:

sh
Copy code
# Step 1: Create service account and cluster role binding
kubectl create serviceaccount dashboard-admin-sa
kubectl create clusterrolebinding dashboard-admin-sa --clusterrole=cluster-admin --serviceaccount=default:dashboard-admin-sa

# Step 2: Generate the token
kubectl -n default create token dashboard-admin-sa



--
helm create resource-server-chart
helm install mychart resource-server-chart
kubectl get pods
kubectl get services

--
D:\dev\Java\git\springboot-angular-auth2-proxy\resource-server\resource-server-chart>helm install resource-server .
D:\dev\Java\git\springboot-angular-auth2-proxy\resource-server\resource-server-chart>helm uninstall resource-server


# Fix Nginx problem ==> install correct version 

To install the NGINX Ingress Controller using kubectl, follow these steps:

Create a Namespace for the Ingress Controller:
Create a dedicated namespace for the NGINX Ingress Controller to keep it organized.


    kubectl create namespace ingress-nginx

Install the NGINX Ingress Controller:
Use the official YAML manifests provided by the NGINX Ingress Controller project to deploy the controller. You can do this by applying the YAML manifest directly from the repository.


    kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/cloud/deploy.yaml
Verify the Installation:
Check that all the components are running properly by listing the pods in the ingress-nginx namespace.


    kubectl get pods -n ingress-nginx

    kubectl get svc -n ingress-nginx

    D:\dev\Java\git\springboot-angular-auth2-proxy\resource-server\resource-server-chart>helm install resource-server .
    D:\dev\Java\git\springboot-angular-auth2-proxy\resource-server\resource-server-chart>helm uninstall resource-server

    PS C:\Users\koffi> kubectl get ingress
NAME                                    CLASS    HOSTS              ADDRESS     PORTS   AGE
resource-server-resource-server-chart   <none>   adjodamawuli.com   localhost   80      7m22s

    kubectl get po -A
kubectl get po -A
NAMESPACE       NAME                                                     READY   STATUS      RESTARTS   AGE
default         resource-server-resource-server-chart-84db8ff756-7zsfg   1/1     Running     0          3s

    kubectl logs resource-server-resource-server-chart-84db8ff756-7zsfg

# Important
add this to c:\Windows\System32\Drivers\etc\hosts
127.0.0.1 adjodamawuli.com