# eq-author-terraform-redis

Terraform project that creates the redis infrastructure for EQ Author

To import this module add the following code into you Terraform project:

```
module "author-redis" {
  source              = "github.com/ONSdigital/eq-author-terraform-redis"
  env                 = "${var.env}-author"
  aws_account_id      = "${var.aws_account_id}"
  aws_assume_role_arn = "${var.aws_assume_role_arn}"
  vpc_id              = "${module.author-vpc.vpc_id}"
  application_cidrs   = "${var.author_application_cidrs}"
  database_subnet_ids = "${module.author-vpc.database_subnet_ids}"
}
```

To run this module on its own run the following code: (Replacing 'XXX' with your values)

```
terraform apply -var "env=XXX" \
                -var "aws_access_key=XXX" \
                -var "aws_secret_key=XXX" \
                -var "slack_alert_sns_arn=XXX"
```
