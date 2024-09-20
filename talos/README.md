# Apply talos configuration
### Master node
```
talosctl apply-config --insecure --nodes <ip> --file controlplane.yaml --config-patch @patch_master.yaml
```
### Worker node
```
talosctl apply-config --insecure --nodes <ip> --file worker.yaml --config-patch @patch_nvidia.yaml
```
