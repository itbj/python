# 2021-01-15  
$ pip install kubernetes | tee n.txt
## Examples

list all pods:

```python
from kubernetes import client, config

# Configs can be set in Configuration class directly or using helper utility
config.load_kube_config()

v1 = client.CoreV1Api()
print("Listing pods with their IPs:")
ret = v1.list_pod_for_all_namespaces(watch=False)
for i in ret.items:
    print("%s\t%s\t%s" % (i.status.pod_ip, i.metadata.namespace, i.metadata.name))
```
Result:  
$ python k2.py
```
/home/taoli/code/py3/lib/python3.8/site-packages/kubernetes/config/kube_config.py:280: YAMLLoadWarning: calling yaml.load() without Loader=... is deprecated, as the default Loader is unsafe. Please read https://msg.pyyaml.org/load for full details.
  config_dict=yaml.load(f),
Listing pods with their IPs:
172.17.0.4      default a1
172.17.0.6      default b3
172.17.0.8      default hello-f45cbcf6d-dg8r6
172.17.0.10     default hello-f45cbcf6d-hh9q2
172.17.0.5      default hello-f45cbcf6d-t24js
172.17.0.7      default hello-f45cbcf6d-tfk7r
172.17.0.11     default nfs-deployment-799cdcf688-lftvx
172.17.0.10     default nginx-deployment-66b6c48dd5-9625m
172.17.0.8      default nginx-deployment-66b6c48dd5-gwpjl
172.17.0.9      default nginx-deployment-66b6c48dd5-m9fsf
```
