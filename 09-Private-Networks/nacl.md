# AWS NACL

In AWS, NACL stands for Network Access Control List. NACLs are stateless, virtual firewalls that control inbound and outbound traffic at the subnet level in a Virtual Private Cloud (VPC). They provide an additional layer of network security by allowing or denying traffic based on rules defined for each subnet.

AWS NACLs have the following characteristics:

1. Stateless: NACLs are stateless, meaning that they do not track the state of traffic flows. Each network flow is evaluated independently based on the rules defined in the NACL.

2. Rule Evaluation Order: NACLs follow a numbered rule evaluation order. The rules are processed in ascending order, starting from the lowest-numbered rule. The first matching rule determines whether the traffic is allowed or denied.

3. Allow or Deny Traffic: Each rule in a NACL specifies whether to allow or deny traffic based on its properties, such as source/destination IP addresses, protocols, and ports.

4. Inbound and Outbound Rules: NACLs have separate sets of inbound and outbound rules. Inbound rules control traffic coming into the subnet, while outbound rules control traffic leaving the subnet.

5. Default Rules: Every NACL has two default rules: one for inbound and one for outbound. By default, inbound traffic is denied, and outbound traffic is allowed. These default rules can be customized as per the specific requirements.

AWS NACLs have two types of rules:

1. Explicit Allow/Deny Rules: These rules are explicitly defined by the user and determine whether traffic is allowed or denied based on specified criteria, such as source/destination IP addresses, protocols, and ports. These rules can be customized to control access to specific resources or limit traffic types.

2. Implicit Deny Rule: At the end of every NACL rule list, there is an implicit deny rule that denies all traffic that doesn't match any of the preceding allow rules. This ensures that any traffic not explicitly allowed is automatically denied.

By configuring NACL rules, you can define granular network access controls at the subnet level within your VPC. NACLs complement the security groups, which operate at the instance level, to provide a layered approach to network security in AWS.
