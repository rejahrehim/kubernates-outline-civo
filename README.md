# Deploy Outline in Civo Kubernetes Cluster 

## Steps

### Create kubernetes cluster in [CIVO](https://www.civo.com)
Spin up a kubernetes cluster in your civo cloud, note down the cluster name you have provided while creating the cluster. Also get the API Key of your account from [Security Section](https://www.civo.com/account/security)

### Spin up Outline
After the cluster is functional(it may take upto 5 mintues), run the following snippet

```
curl -L -s https://git.io/JUVkD | bash -s <api_key> <cluster_name>
```

replace <api_key> and <cluster_name> with your account's api key and cluster name that you have provided.

make sure you have satisfied the following dependencies before running the snippet:

* kubectl
* git
* curl
* openssl

After the script is completed copy the installation output `{"apiUrl":"https://xxx.xxx.xxx.xxx:8081/xxxxxxxxxxxxx","certSha256":"XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"}` and make sure to check all containers are up and running before pasting the output to outline manager application.

To check container status change directory to `/tmp/civo-outline` and run `kubectl get pods --all-namespaces --kubeconfig config`

If all containers are running then copy paste the installation output to outline manager.
