### Prerequisites

A k8s kubernetes cluster using k3s is needed to be setup first. To setup a k8s cluster follow the guide [here](https://mrc-ide.myjetbrains.com/youtrack/articles/RESIDE-A-31/Setting-up-Kubernetes-k8s-Cluster).

### Running

Run `./start-k8s <env>` to run the shiny server in k8s. You will need your github access token, as vault access is needed for secrets.

#### Updating deployment 

To make updates to update specific deployment. i.e when new code has been deployed and new image is created. 
Run the following `kubectl rollout restart deployment <depl_name>`. replace <depl_name> with deployment you want to replace.

To scale deployment run `kubectl scale deployment/<depl_name> --replicas=<num_replicas>`. replace <depl_name> with deployment name and <num_replicas> with number of replicas you want to scale to.

To check all deployments run `kubectl get deploy -n beebop`.
### Teardown

Run `./teardown-k8s <env>`
