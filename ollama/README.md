# Install nvidia stuff
```
helm repo add nvdp https://nvidia.github.io/k8s-device-plugin
helm repo update
helm upgrade -i nvdp nvdp/nvidia-device-plugin \
    --version=0.16.1 \
    --namespace nvidia-device-plugin \
    --create-namespace \
    --set gfd.enabled=true
```
# Install ollama
```
helm repo add ollama-helm https://otwld.github.io/ollama-helm/
helm repo update
helm install ollama ollama-helm/ollama --namespace ollama --create-namespace -f values.yaml
```

>[!WARNING]
>If you want to use a GPU with your setup make sure to use processor type "host" in your hypervisor. I had troubles with other processor types.
