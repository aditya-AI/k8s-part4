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

## IAM S3 Policy

```bash
aws iam create-policy --policy-name S3ListTest --policy-document file://k8s-manifests/iam-s3-test-policy.json
103877285477
# test policy is created
aws iam get-policy-version --policy-arn arn:aws:iam::ACCOUNT_ID:policy/S3ListTest --version-id v1
```

## Create Cluster

```bash
eksctl create cluster -f k8s-manifests/eks-cluster.yaml
```

## Enable IAM OIDC Provider

```bash
eksctl utils associate-iam-oidc-provider --region ap-south-1 --cluster basic-cluster --approve
```

## Create IAM Role for Service Account

```bash
eksctl create iamserviceaccount \
  --name s3-list-sa \
  --cluster basic-cluster \
  --attach-policy-arn arn:aws:iam::103877285477:policy/S3ListTest \
  --approve \
	--region ap-south-1
```