Jupyter Notebooks for Kubernetes
================================

This is a set of Jupyter notebooks to learn the Kubernetes API in Python.

Launch the deployment and create the service.

```
kubectl create -f docker/jupyter.yml
```

Open your browser on the jupyter service and go through the notebooks.

If you are using minikube, you can run this command to see jupyter service in your browser:

```
minikube service jupyter
```

## 注释  

https://github.com/itbj/python/blob/master/examples/notebooks/create_pod.ipynb 
```
config.load_incluster_config() #should be changed to new command. otherwise error to run.
```

#Configs can be set in Configuration class directly or using helper utility  
```
config.load_kube_config()
```
