# terraform-aws-eks
> deploy a kubernetes cluster using terraform aws eks resources

## requirements

  - jq
  - awscli
  - kubetcl
  - aws-iam-authenticator
  - terraform @ >= 0.12

## usage

```sh
# provision with terraform
cd src
terraform init
terraform plan
terraform apply

# add new context to ~/.kube/config
aws eks update-kubeconfig --name <cluster_name> # test-eks-ajdev

# checks
kubectl version
kubetctl get nodes
kubectl config current-context
kubectl config view
```

```sh
# wip
./oneclick deploy
./oneclick destroy
```

## references

  - [GH - terraform-aws-modules/terraform-aws-eks](https://github.com/terraform-aws-modules/terraform-aws-eks)
  - [GH - WesleyCharlesBlake/terraform-aws-eks](https://github.com/WesleyCharlesBlake/terraform-aws-eks)
  - [Blog - AWS EKS Introduction](https://learn.hashicorp.com/terraform/aws/eks-intro)