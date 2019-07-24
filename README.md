# eq-author-terraform-waf

Terraform project that creates the WAF infrastructure for EQ Author

To import this module add the following code into you Terraform project:

```
module "author-waf" {
  source              = "github.com/ONSdigital/eq-author-terraform-waf"
  env                 = "${var.env}-author"
  aws_account_id      = "${var.aws_account_id}"
  aws_assume_role_arn = "${var.aws_assume_role_arn}"
  external_alb_arn   = "${var.external_alb_arn}"
  metric_prefix       = "${var.metric_prefix"}
}
```

To run this module on its own run the following code: (Replacing 'XXX' with your values)

```
terraform apply -var "env=XXX" \
                -var "aws_access_key=XXX" \
                -var "aws_secret_key=XXX" \
                -var "slack_alert_sns_arn=XXX"
```
