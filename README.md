# terraform-aws-eks
> deploy a kubernetes cluster using terraform aws eks resources

## requirements

  - jq
  - awscli
  - kubetcl
  - aws-iam-authenticator
  - terraform @ >= 0.12

## usage

To start the application, you can run `./oneclick deploy`, which essentially runs these commands, but with auto approve:
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

To bring down the application you can run `./oneclick destroy`, which essentially runs these commands, but with auto approve:
```sh
# destroy infrastructure
cd terraform
terraform destroy -auto-approve
rm -rf .terraform terraform.tfstate*
```

## references

  - [GH - terraform-aws-modules/terraform-aws-eks](https://github.com/terraform-aws-modules/terraform-aws-eks)
  - [GH - WesleyCharlesBlake/terraform-aws-eks](https://github.com/WesleyCharlesBlake/terraform-aws-eks)
  - [Blog - AWS EKS Introduction](https://learn.hashicorp.com/terraform/aws/eks-intro)