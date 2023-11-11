# Kubernetes - IV: IRSA, Volumes, ISTIO & KServe

In this session, we deploy SDXL model on Kubernetes using KServe. The application is exposed via a Load Balancer. The resulting deployment can be monitored for various parameters and can be visualized in tools like Kiali, Prometheus, and Grafana.

```bash
cd torchserve-mar
pip install -r requirements.txt 
python download_sdxl.py
bash model_zip.sh
```

docker run -it --rm --shm-size=1g --ulimit memlock=-1 --ulimit stack=67108864 --gpus all -v `pwd`:/opt/src pytorch/torchserve:0.8.1-gpu bash

