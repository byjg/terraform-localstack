# terraform-localstack

Apply a terraform plan on Localstack

## Instructions


Change the `docker-compose.yaml` to add the desired services. 

The new localstack exposes the port 4566 for all services. 

```
docker-compose up -d 
```

## Testing if the connection is working:

```
export AWS_ACCESS_KEY_ID=foo
export AWS_SECRET_ACCESS_KEY=bar
export AWS_REGION=us-east-1

aws --endpoint-url=http://localhost:4566 s3 mb s3://local-bucket
aws --endpoint-url=http://localhost:4566 s3 ls
```

## Run the terraform plan/apply

To run the example provided just do:

```
terraform init
terraform plan
terraform apply
```


## References

* https://registry.terraform.io/providers/hashicorp/aws/latest/docs/guides/custom-service-endpoints#localstack
* https://github.com/localstack/localstack




