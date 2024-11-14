# AWS RDS and Aurora Serverless Checklist with Terraform

## Common Essential Components (RDS & Aurora)

- [ ] Define database engine and version:
  - Engine type (MySQL, PostgreSQL, etc.)
  - Engine version
  - Parameter group family
- [ ] Configure instance specifications:
  - Instance class
  - Storage type and size
  - Multi-AZ deployment
- [ ] Network configuration:
  - VPC and subnet placement (DB subnet group)
  - Security groups
  - Public accessibility setting
- [ ] Authentication settings:
  - Master username and password
  - IAM database authentication
  - Password policies
- [ ] Configure backup settings:
  - Backup retention period
  - Backup window
  - Final snapshot configuration
- [ ] Set up monitoring:
  - Enhanced monitoring
  - Performance insights
  - CloudWatch logs export

## RDS Specific Components

- [ ] Storage configuration:
  - Allocated storage
  - Max allocated storage
  - Storage type (gp2, gp3, io1)
  - Storage autoscaling
- [ ] Configure maintenance:
  - Maintenance window
  - Auto minor version upgrade
- [ ] Set up read replicas (if needed):
  - Number of replicas
  - Replica regions
  - Replica instance class
- [ ] Configure option groups:
  - Engine-specific options
  - Custom options

## Aurora Specific Components

- [ ] Cluster configuration:
  - Cluster identifier
  - Engine mode (provisioned/serverless)
  - Replication source
- [ ] Configure endpoints:
  - Cluster endpoint
  - Reader endpoint
  - Custom endpoints
- [ ] Set up auto scaling:
  - Minimum and maximum ACU
  - Target metrics
  - Scale-in/out policies

## Aurora Serverless Specific

- [ ] Configure scaling:
  - Minimum and maximum capacity units
  - Auto pause configuration
  - Seconds before auto pause
  - Force scaling points
- [ ] Data API settings:
  - Enable/disable Data API
  - Configure HTTP endpoint
- [ ] Set up capacity management:
  - Timeout action
  - Capacity allocation strategy
- [ ] Configure serverless v2 specific settings (if using v2):
  - Base capacity
  - Maximum capacity
  - Minimum capacity

## High Availability Components

- [ ] Configure Multi-AZ deployment
- [ ] Set up read replicas
- [ ] Configure failover priority
- [ ] Set up cross-region replicas (if needed)
- [ ] Configure automatic failover
- [ ] Set up promotion tiers

## Security Components

- [ ] Configure encryption:
  - At-rest encryption (KMS)
  - In-transit encryption (SSL/TLS)
- [ ] Set up security groups:
  - Inbound rules
  - Outbound rules
- [ ] Configure IAM:
  - Instance roles
  - User permissions
- [ ] Set up SSL/TLS:
  - Certificate configuration
  - Force SSL connections
- [ ] Configure network security:
  - Network ACLs
  - Route tables
  - VPC endpoints

## Monitoring and Management

- [ ] Enable enhanced monitoring
- [ ] Set up performance insights
- [ ] Configure CloudWatch:
  - Metric alarms
  - Log groups
  - Dashboard
- [ ] Set up event notifications:
  - SNS topics
  - Event subscriptions
- [ ] Configure audit logging:
  - Audit logs
  - Error logs
  - General logs
  - Slow query logs

## Best Practices

- [ ] Implement proper backup strategy
- [ ] Configure appropriate parameter groups
- [ ] Set up proper monitoring and alerting
- [ ] Implement proper security controls
- [ ] Configure appropriate maintenance windows
- [ ] Document database configuration
- [ ] Set up cost allocation tags
- [ ] Configure appropriate instance sizing

## Terraform AWS Provider Documentation References

### Core RDS Resources

- [aws_db_instance](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_instance)
- [aws_db_parameter_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_parameter_group)
- [aws_db_subnet_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_subnet_group)
- [aws_db_option_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_option_group)

### Aurora Resources

- [aws_rds_cluster](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/rds_cluster)
- [aws_rds_cluster_instance](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/rds_cluster_instance)
- [aws_rds_cluster_parameter_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/rds_cluster_parameter_group)
- [aws_rds_cluster_endpoint](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/rds_cluster_endpoint)

### Security Resources

- [aws_db_security_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_security_group)
- [aws_security_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group)
- [aws_kms_key](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/kms_key)
- [aws_iam_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role)

### Monitoring Resources

- [aws_cloudwatch_metric_alarm](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudwatch_metric_alarm)
- [aws_cloudwatch_log_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudwatch_log_group)
- [aws_sns_topic](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/sns_topic)
- [aws_db_event_subscription](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_event_subscription)

### Backup and Snapshot Resources

- [aws_db_snapshot](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_snapshot)
- [aws_db_cluster_snapshot](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/db_cluster_snapshot)

### Data Sources

- [aws_rds_cluster](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/rds_cluster)
- [aws_db_instance](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/db_instance)
- [aws_db_snapshot](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/db_snapshot)
- [aws_rds_engine_version](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/rds_engine_version)
- [aws_rds_orderable_db_instance](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/rds_orderable_db_instance)
