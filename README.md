# Kubernetes - IV: IRSA, Volumes, ISTIO & KServe

In this session, we deploy SDXL model on Kubernetes using KServe. The application is exposed via a Load Balancer. The resulting deployment can be monitored for various parameters and can be visualized in tools like Kiali, Prometheus, and Grafana.

```bash
cd torchserve-mar
pip install -r requirements.txt 
python download_sdxl.py
bash model_zip.sh
```

docker run -it --rm --shm-size=1g --ulimit memlock=-1 --ulimit stack=67108864 --gpus all -v $(pwd):/opt/src pytorch/torchserve:0.8.1-gpu bash

Create MAR from handler and model artifact

cd /opt/src
torch-model-archiver --model-name sdxl --version 1.0 --handler sdxl_handler.py --extra-files sdxl-1.0-model.zip -r requirements.txt

This will create sdxl.mar

Create a S3 Bucket where we will store these model .mar files, which will be loaded by KServe
aws s3 cp config.properties s3://pytorch-models/config/
aws s3 cp sdxl.mar s3://pytorch-models/model-store/
