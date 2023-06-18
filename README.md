deploy devops tools in eks cluster with helm charts

To pull helm chart locally 
helm pull prometheus-community/prometheus --untar --untardir ./charts
==========================
Steps to deploy charts:-
1- Create helm-charts repo in code commit manually
2- Create code build and code pipeline
3- Deploy charts through buildspec.yaml 

===========================
Notes:-
Provide eks access to the code build 
Create Namesapce manually for Obserevability stack 
Deploy the charts 
=============================
ALB to NLB :- 
Ineternal NLB:- 
1- Create a listener and a target group for each service
2- Create TargetGroupBinding 
---
apiVersion: elbv2.k8s.aws/v1beta1
kind: TargetGroupBinding
metadata:
  name: my-tgb
spec:
  serviceRef:
    name: awesome-service # route traffic to the awesome-service
    port: 80
  targetGroupARN: <arn-to-targetGroup>
---
External ALB :-
1- Create a target group for the new NLB listener (NLB Ip will be same but port will be change)
2- Add new rule in the existing listener 


=============================
