  Below we are trying to deploy application and its related yaml files into the EKS clusters using Helm : 

1. Create a helm chart using the below command : 

Helm create my-test-helmchart

This command will create the tree structure of helm files, directories such as Chart.yaml, charts, Templates, values.yaml 

2.  Prepare the kubernetes application related config files in the templates and the values if you are using it.

3. Make sure you create the EKS cluster and node group and you have access to create EKS resources from where you are running helm commands.

4. Authenticate the eks cluster by running the update-config command as below : 

  aws eks --region  us-east-1 update-kubeconfig --name test-cluster5

5. To check if there are any issues with the helm chart, use the below command : 

  Navigate to the path of Helm location and run Helm lint . 

6. Deploy the Helm by using the commands : 
 
 Helm install test-chart .

7. Once you have written your parameterised yaml template files and provided the appropriate values in the values.yaml file, run the below command to cross verify what are the values the template files are going to feed with.

 Helm template . > test.yaml

You can verify the contents in test.yaml file. 
