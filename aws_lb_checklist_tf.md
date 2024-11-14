# AWS Load Balancer Checklist with Terraform

## Common Essential Components (ALB & NLB)

- [ ] Define load balancer type (application or network)
- [ ] Configure basic settings:
  - Name
  - Internal/Internet-facing
  - IP address type (ipv4 or dualstack)
  - Subnets (minimum of 2 for HA)
- [ ] Set up target groups:
  - Target type (instance, IP, or Lambda)
  - Protocol and port
  - Health check settings
- [ ] Configure listeners:
  - Protocol and port
  - Default actions
- [ ] Set up tags
- [ ] Enable deletion protection (if needed)
- [ ] Configure access logs

## Application Load Balancer (ALB) Specific

- [ ] Configure security groups
- [ ] Set up listener rules:
  - Path patterns
  - Host-based routing
  - HTTP header conditions
  - Query string parameters
  - Source IP address
- [ ] Configure SSL/TLS certificates:
  - Default certificate
  - Optional certificate list
- [ ] Set up redirect rules (HTTP to HTTPS)
- [ ] Configure authentication:
  - OIDC
  - Cognito
- [ ] Set up fixed response actions
- [ ] Configure slow start duration
- [ ] Set up WAF association (if needed)

## Network Load Balancer (NLB) Specific

- [ ] Configure cross-zone load balancing
- [ ] Set up TLS certificates (if using TLS listeners)
- [ ] Configure preservation of client IP addresses
- [ ] Set up elastic IPs (if needed)
- [ ] Configure health check settings:
  - Protocol
  - Port
  - Interval
  - Threshold counts
- [ ] Set up connection idle timeout
- [ ] Configure stickiness (if needed)

## High Availability Components

- [ ] Deploy across multiple AZs
- [ ] Configure failover routing policies
- [ ] Set up health checks with proper thresholds
- [ ] Configure backup targets
- [ ] Set up CloudWatch alarms for:
  - Unhealthy hosts
  - Request count
  - Latency
  - Error rates

## Monitoring and Management

- [ ] Enable access logging
- [ ] Set up CloudWatch metrics
- [ ] Configure SNS notifications
- [ ] Set up monitoring dashboards
- [ ] Configure metric-based alarms
- [ ] Enable request tracing (ALB)

## Security Components

- [ ] Configure security groups (ALB)
- [ ] Set up SSL/TLS policies
- [ ] Configure authentication (ALB)
- [ ] Set up WAF rules (ALB)
- [ ] Enable Shield protection (if needed)

## Best Practices

- [ ] Implement proper tagging strategy
- [ ] Configure appropriate idle timeout values
- [ ] Set up proper security group rules
- [ ] Implement proper SSL/TLS policies
- [ ] Configure appropriate health check settings
- [ ] Document load balancer configuration
- [ ] Set up cost allocation tags

## Terraform AWS Provider Documentation References

### Core Load Balancer Resources

- [aws_lb](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb)
- [aws_lb_target_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_target_group)
- [aws_lb_target_group_attachment](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_target_group_attachment)
- [aws_lb_listener](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_listener)
- [aws_lb_listener_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_listener_rule)

### SSL/TLS Resources

- [aws_acm_certificate](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/acm_certificate)
- [aws_acm_certificate_validation](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/acm_certificate_validation)
- [aws_lb_listener_certificate](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_listener_certificate)

### Security Resources

- [aws_security_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group)
- [aws_wafv2_web_acl_association](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/wafv2_web_acl_association)
- [aws_lb_cookie_stickiness_policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_cookie_stickiness_policy)

### Monitoring Resources

- [aws_cloudwatch_metric_alarm](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudwatch_metric_alarm)
- [aws_sns_topic](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/sns_topic)
- [aws_cloudwatch_log_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudwatch_log_group)

### Authentication Resources

- [aws_cognito_user_pool](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cognito_user_pool)
- [aws_cognito_user_pool_client](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cognito_user_pool_client)

### Data Sources

- [aws_lb](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/lb)
- [aws_lb_target_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/lb_target_group)
- [aws_lb_listener](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/lb_listener)
- [aws_acm_certificate](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/acm_certificate)
