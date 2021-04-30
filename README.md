## Amazon VPC Enpoints

Understanding Concepts

**VPC Endpoint**
- A VPC Endpoint give us permission to create a private connect to a service, this service can be an AWS Service, AWS Marketplace Partner or another AWS account.
- Actualy AWS makes available three types of endpoints: Gateway Endpoint, Interface Endpoint and Gateway Load Balancer endpoint.
- The VPC Endpoint is created in the AWS Consumer account to make possible the access to the Provider service.
	
**Endpoint Service**
- It's the entrypoint to the service/application present in the account that we want to make available to other services or AWS accounts through a private connection.
- In other words is used for other AWS principals to connect to our VPC. In this case they should create a VPC Endpoint to make a private connection to our services.

**PrivateLink**
- The technology that provides private connectivity between VPCs and services.
- To use AWS PrivateLink, create a VPC endpoint for a service in your VPC. You create the type of VPC endpoint required by the supported service. This creates an elastic network interface in your subnet with a private IP address that serves as an entry point for traffic destined to the service.

![alt text](https://d2908q01vomqb2.cloudfront.net/5b384ce32d8cdef02bc3a139d4cac0a22bb029e8/2018/07/26/rsz_privatelink-blog-diagram.jpg)

### Cloudformation Templates

- We can use **[cloudformation](https://aws.amazon.com/pt/cloudformation/)** templates (I've made some examples available in this repository) to create the endpoints aboved mentioned.
- It's possible to pass cloudformation parameters through a json file when using AWS CLI to create Stacks, **parameters.json** is the example parameters for the template-vpc-endpoint-service.yml template.

**References**
- https://docs.aws.amazon.com/vpc/latest/privatelink/endpoint-services-overview.html
- https://rivery.io/docs/configuring-aws-privatelink
