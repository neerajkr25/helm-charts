# Prometheus
helm pull prometheus-community/prometheus --untar --untardir ./charts

# CBS driver setup :- 
aws eks create-addon --cluster-name uat-cluster --region ap-south-1 --addon-name aws-ebs-csi-driver \
  --service-account-role-arn arn:aws:iam::423224728550:role/AmazonEKS_EBS_CSI_DriverRole