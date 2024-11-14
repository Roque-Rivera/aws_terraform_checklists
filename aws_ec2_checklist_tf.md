# AWS EC2 Checklist with Terraform

## Essential Components

- [ ] Define EC2 instance type and size
- [ ] Select appropriate AMI (Amazon Machine Image)
- [ ] Configure root volume:
  - Size
  - Volume type (gp2, gp3, io1, etc.)
  - Delete on termination setting
- [ ] Configure network settings:
  - VPC and subnet placement
  - Auto-assign public IP (if needed)
  - Primary network interface
- [ ] Set up security groups
- [ ] Configure IAM instance profile (role)
- [ ] Create and assign SSH key pair
- [ ] Configure user data (bootstrap scripts)
- [ ] Set up instance tags (including Name tag)

## Storage Components

- [ ] Configure additional EBS volumes:
  - Volume size and type
  - Device names
  - Encryption settings
- [ ] Set up EBS snapshots policy
- [ ] Configure instance store volumes (if applicable)

## High Availability Components

- [ ] Set up Auto Scaling Group
- [ ] Configure launch template or launch configuration
- [ ] Define scaling policies:
  - Target tracking
  - Step scaling
  - Simple scaling
- [ ] Set up instance health checks
- [ ] Configure placement groups (if needed)

## Monitoring and Management

- [ ] Enable detailed monitoring
- [ ] Set up CloudWatch agent
- [ ] Configure Systems Manager agent (SSM)
- [ ] Set up backup policies
- [ ] Configure maintenance window
- [ ] Enable termination protection (if needed)

## Optional Components

- [ ] Elastic IP association
- [ ] Load balancer registration
- [ ] Enhanced networking
- [ ] EC2 instance connect
- [ ] Spot instance configuration
- [ ] CPU credits (for T-class instances)
- [ ] Capacity reservations
- [ ] Dedicated host assignments
- [ ] Instance metadata service (IMDSv2)

## Best Practices

- [ ] Implement proper tagging strategy
- [ ] Use parameter store for sensitive data
- [ ] Implement proper backup strategy
- [ ] Configure automatic recovery
- [ ] Use latest generation instance types
- [ ] Implement proper security hardening
- [ ] Document instance configuration
- [ ] Set up cost allocation tags

## Terraform AWS Provider Documentation References

### Core EC2 Resources

- [aws_instance](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance)
- [aws_ami](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ami)
- [aws_key_pair](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/key_pair)
- [aws_launch_template](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/launch_template)
- [aws_launch_configuration](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/launch_configuration)

### Auto Scaling Resources

- [aws_autoscaling_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/autoscaling_group)
- [aws_autoscaling_policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/autoscaling_policy)
- [aws_autoscaling_schedule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/autoscaling_schedule)
- [aws_autoscaling_attachment](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/autoscaling_attachment)

### Storage Resources

- [aws_ebs_volume](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ebs_volume)
- [aws_volume_attachment](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/volume_attachment)
- [aws_ebs_snapshot](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ebs_snapshot)

### Network Resources

- [aws_network_interface](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/network_interface)
- [aws_network_interface_attachment](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/network_interface_attachment)
- [aws_eip](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/eip)
- [aws_eip_association](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/eip_association)

### Security Resources

- [aws_security_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group)
- [aws_iam_instance_profile](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_instance_profile)
- [aws_placement_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/placement_group)

### Monitoring Resources

- [aws_cloudwatch_metric_alarm](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudwatch_metric_alarm)
- [aws_sns_topic](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/sns_topic)

### Data Sources

- [aws_ami](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/ami)
- [aws_ec2_instance_type](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/ec2_instance_type)
- [aws_ec2_instance_types](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/ec2_instance_types)
- [aws_instances](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/instances)
- [aws_availability_zones](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/availability_zones)
