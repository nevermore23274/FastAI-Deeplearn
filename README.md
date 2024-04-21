# Fast AI Training
This is a repo for the training located at https://www.fast.ai/ that simply contains my notebooks and container.

# Jupyter Notebook

- `podman build -t pytorch-jupyter -f docker/Dockerfile .`
- `podman run -p 8888:8888 -v $(pwd):/workspace:Z pytorch-jupyter`

- Navigate to: 
`http://localhost:8888/`

- If you installed the Nvidia Container Toolkit and wish to use GPU: (see https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/cdi-support.html)

- `podman run --hooks-dir=/usr/share/containers/oci/hooks.d --gpus all -p 8888:8888 -v $(pwd):/workspace:z pytorch-jupyter`

NOTE: If you created this container and have since updated your drivers, you'll need to regenerate the CDI specification with `sudo nvidia-ctk cdi generate --output=/etc/cdi/nvidia.yaml`

