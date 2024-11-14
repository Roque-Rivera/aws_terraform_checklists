# AWS VPC Checklist with Terraform

## Essential Components (Missing from original)

- [ ] Create an Internet Gateway and attach it to the VPC (Required for public internet access)
- [ ] Configure CIDR blocks for VPC and subnets
- [ ] Enable DNS hostnames and DNS support for the VPC
- [ ] Configure Network ACLs (NACLs) for additional subnet security
- [ ] Set up VPC Flow Logs for network monitoring and troubleshooting

## Original Components (All Required)

- [ ] Create a VPC
- [ ] Create all the subnets
- [ ] Create a Route Table for every layer:
  - Public Subnet Route Table - to internet gateway
  - Private Subnet Route Table - to NAT gateway
  - Database Subnet Route Table - no internet access
- [ ] Create a default Security Group for the VPC
- [ ] Create a NAT Gateway for internet access in private subnets
- [ ] Create Route Table Associations for public and private subnets
- [ ] Create a DHCP Options Set and Associate it to the VPC

## Optional Components (Depending on Requirements)

- [ ] VPC Endpoints for AWS Services (S3, DynamoDB, etc.)
- [ ] Transit Gateway attachments for connecting to other VPCs
- [ ] VPC Peering connections
- [ ] AWS PrivateLink configurations
- [ ] Custom DHCP option sets (if using custom DNS servers)
- [ ] AWS Network Firewall
- [ ] VPN Connections:
  - Site-to-Site VPN
  - Client VPN endpoints
- [ ] Direct Connect configurations

## Best Practices

- [ ] Implement proper tagging strategy for all resources
- [ ] Plan IP address space carefully using CIDR blocks
- [ ] Configure backup NAT Gateways in different AZs for high availability
- [ ] Implement proper subnet sizing based on workload requirements
- [ ] Set up monitoring and alerting for VPC resources
- [ ] Document network architecture and security group rules

## Terraform AWS Provider Documentation References

### Core VPC Resources

- [aws_vpc](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc)
- [aws_subnet](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/subnet)
- [aws_internet_gateway](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/internet_gateway)
- [aws_route_table](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route_table)
- [aws_route_table_association](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route_table_association)
- [aws_nat_gateway](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/nat_gateway)

### Security Resources

- [aws_security_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group)
- [aws_network_acl](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/network_acl)
- [aws_network_acl_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/network_acl_rule)
- [aws_network_firewall_rule_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/networkfirewall_rule_group)

### DNS and DHCP Resources

- [aws_vpc_dhcp_options](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc_dhcp_options)
- [aws_vpc_dhcp_options_association](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc_dhcp_options_association)

### Monitoring and Logging

- [aws_flow_log](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/flow_log)

### VPC Connectivity Resources

- [aws_vpc_endpoint](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc_endpoint)
- [aws_vpc_peering_connection](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpc_peering_connection)
- [aws_vpn_connection](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/vpn_connection)
- [aws_dx_connection](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/dx_connection)
- [aws_ec2_transit_gateway](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ec2_transit_gateway)
- [aws_ec2_transit_gateway_vpc_attachment](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ec2_transit_gateway_vpc_attachment)

### Data Sources

- [aws_vpc](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/vpc)
- [aws_subnet](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/subnet)
- [aws_subnets](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/subnets)
- [aws_availability_zones](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/availability_zones)
- [aws_security_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/security_group)
