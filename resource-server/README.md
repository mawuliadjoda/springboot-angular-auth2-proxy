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