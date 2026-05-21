# Newsletter Error Log — 2026-05-21

## Run Details

- **Date and time of failed run:** 2026-05-21
- **Failure point:** Gmail draft creation returned "MCP tool call requires approval" — tool execution was blocked pending user permission approval in the remote execution environment.

---

## Workflow Status Checklist

1. **CLAUDE.md found and read:** Yes — read successfully from `/home/user/Career-and-certs-daily-newsletter/CLAUDE.md`.
2. **career_roadmap_v3_sprint.md found and read:** Yes — read successfully from `context/career_roadmap_context/career_roadmap_v3_sprint.md`.
3. **career_roadmap_v3_sprint.pdf checked as backup/reference:** Not required — Markdown file was complete and clear.
4. **Today's roadmap topic successfully extracted:** Yes. May 21 has no exact date match in the roadmap. Nearest upcoming topic is May 22: AWS SAA — VPC Deep Dive (NACLs vs Security Groups, VPC Peering, Endpoints, Transit Gateway, Flow Logs).
5. **Roadmap topic extracted:** AWS SAA — VPC Deep Dive (NACLs vs SGs, peering, endpoints, Transit Gateway, Flow Logs) — nearest upcoming topic for May 22.
6. **Newsletter generated:** Yes — full newsletter was generated and is included below.
7. **Gmail direct sending attempted:** Not attempted — no direct send tool is available; only `mcp__Gmail__create_draft` is available.
8. **Gmail direct sending succeeded or failed:** N/A — not attempted.
9. **Gmail draft creation attempted:** Yes.
10. **Gmail draft creation succeeded or failed:** Failed — MCP tool call requires approval. The environment blocked the call pending user permission.

---

## Exact Failure Point

`mcp__Gmail__create_draft` returned error: `Streamable HTTP error: Error POSTing to endpoint: MCP tool call requires approval`

The tool schema was loaded and the call was well-formed. The environment requires the user to approve Gmail MCP tool calls before they execute.

---

## Likely Cause

The Claude Code remote execution environment requires user approval for Gmail MCP tool calls. The permission for `mcp__Gmail__create_draft` has not been pre-approved in project or user settings. This is a permissions/authorization issue in the environment configuration, not a problem with the newsletter content or generation logic.

---

## Steps Taken Before Failure

1. Read CLAUDE.md in full.
2. Read `context/career_roadmap_context/career_roadmap_v3_sprint.md` in full.
3. Identified today's date as May 21, 2026.
4. Confirmed no exact date match for May 21; identified nearest upcoming topic as May 22 (VPC Deep Dive).
5. Generated the complete newsletter per all CLAUDE.md rules.
6. Loaded `mcp__Gmail__create_draft` tool schema via ToolSearch.
7. Attempted to call `mcp__Gmail__create_draft` with the full newsletter body targeting `nruppatel439@gmail.com`.
8. Tool call blocked by environment approval requirement.

---

## Recommended Fix Before Next Run

Option 1 (recommended): In Claude Code settings, add `mcp__Gmail__create_draft` (and optionally `mcp__Gmail__send` if available) to the allowed tools list so that Gmail draft creation executes automatically without requiring per-call approval. This can be configured via the `/update-config` skill or by editing `.claude/settings.json`.

Option 2: When prompted for approval during the run, approve the Gmail MCP tool call manually. The newsletter content is correct and ready to send.

Option 3: Copy the full newsletter body below and paste it manually into Gmail to send to `nruppatel439@gmail.com` with subject: `Daily Career Roadmap Newsletter - May 21, 2026 - AWS SAA: VPC Deep Dive`.

---

## Full Newsletter Body

Subject: Daily Career Roadmap Newsletter - May 21, 2026 - AWS SAA: VPC Deep Dive

---

Every hour you delay is a permanent debt you owe your future self, and unlike money, time cannot be borrowed back. Stop treating your goals like a plan and start treating them like a deadline that already passed.

---

Date: May 21, 2026
Roadmap Topic: AWS SAA — VPC Deep Dive (NACLs vs Security Groups, VPC Peering, Endpoints, Transit Gateway, Flow Logs)
Note: May 21 does not have an exact match in the roadmap. This newsletter covers the nearest upcoming topic scheduled for May 22.
Phase: Phase 2 — AWS Solutions Architect Associate (SAA-C03)
Certification Target: AWS Solutions Architect Associate (SAA-C03) — Deadline June 15, 2026

---

WHAT YOU MUST BE ABLE TO EXPLAIN OR DO AFTER STUDYING THIS TOPIC

- Explain the difference between NACLs and Security Groups: how each works, why one is stateful and the other is stateless, and when you would choose each.
- Describe VPC peering limitations, specifically why it is not transitive and when Transit Gateway is the right replacement.
- Explain VPC Gateway Endpoints vs Interface Endpoints: which services each covers, cost differences, and how they improve security.
- Describe how Transit Gateway replaces a peering mesh at scale and supports hybrid connectivity.
- Explain what VPC Flow Logs capture, how they differ from CloudTrail, and how they support both security monitoring and compliance.
- Design a multi-tier VPC architecture: public and private subnets, route tables, SGs, NACLs, and endpoints working together.

---

DEEP FUNDAMENTALS

VPC (Virtual Private Cloud) is the networking foundation of everything you deploy on AWS. Every EC2 instance, RDS database, and Lambda function in a VPC is governed by the primitives in this topic. If you misconfigure this layer, you either expose your workloads to the internet or lock them down so tightly that nothing functions. This is not optional knowledge — it appears on every SAA exam and in almost every cloud architecture interview.


NACLs vs Security Groups

This is one of the most tested distinctions in SAA and one of the most misunderstood in real environments.

Security Groups (SGs) are stateful firewalls attached to ENIs (Elastic Network Interfaces). Stateful means: if you allow inbound traffic on port 443, the response traffic is automatically allowed outbound. You do not need to write a separate outbound rule for return traffic. Security Groups only support allow rules. They cannot deny. SGs can reference other SGs by ID (useful for tiered architectures: "allow traffic from the app-server SG to the DB SG").

NACLs (Network Access Control Lists) are stateless firewalls attached to subnets. Stateless means: you must explicitly allow both inbound AND outbound traffic. NACLs support both allow and deny rules, evaluated in numerical order (lowest number first). Rule 100 is evaluated before rule 200. Processing stops at the first matching rule.

When to use a NACL: to explicitly block a specific IP address or CIDR at the subnet level. This is something you cannot do with a Security Group alone, since SGs only allow. In incident response, when a SOC determines a source IP is actively attacking, the playbook will include adding a NACL deny rule to cut off that IP across every resource in the targeted subnet immediately.

The most common NACL mistake: forgetting ephemeral ports. When a client connects to your EC2 on port 80, the server sends its response back using an ephemeral port (typically in the range 1024-65535, but verify exact ranges from AWS documentation). Your NACL outbound rules must explicitly allow this port range. Security Groups handle this automatically because they are stateful. NACLs do not — your NACL outbound rule for port 80 inbound traffic is not sufficient; you must also add an outbound rule allowing TCP 1024-65535 back to the client.


VPC Peering

VPC peering connects two VPCs so their resources can communicate as if on the same private network. Traffic routes through the AWS backbone — no public internet, no Internet Gateway required.

Key limitations to memorize:
- Not transitive. If VPC-A peers with VPC-B, and VPC-B peers with VPC-C, VPC-A cannot reach VPC-C through VPC-B. You must create a direct peering connection between A and C if they need to communicate. This is tested directly on the SAA exam.
- Cannot peer VPCs with overlapping CIDR ranges.
- Does not support edge-to-edge routing (cannot route traffic through a VPN or Direct Connect gateway attached to the peer VPC).

Peering works well for 2-5 VPCs. Once you reach 10 or more VPCs, managing the number of peering connections becomes operationally complex. This is the exact problem Transit Gateway solves.


VPC Endpoints

VPC endpoints let your resources in private subnets access AWS services without sending traffic through the public internet. No Internet Gateway, no NAT Gateway required.

Two endpoint types:

Gateway Endpoints — support only S3 and DynamoDB. They are free. A route table entry directs matching traffic to the endpoint rather than the internet. You attach an endpoint policy to control which S3 buckets or DynamoDB tables can be accessed.

Interface Endpoints (PrivateLink) — support virtually every other AWS service: SQS, Secrets Manager, Systems Manager, CloudWatch, EC2 API, KMS, etc. An Interface Endpoint creates an ENI in your subnet with a private IP address. Traffic to the AWS service resolves to this private IP. Interface Endpoints incur a per-hour cost plus a per-GB data transfer cost (verify current pricing from AWS documentation before designing for cost optimization).

A common real-world cost problem: teams provision a NAT Gateway for general internet access, not realizing their EC2 instances in private subnets are routing all S3 traffic through it. NAT Gateway charges per GB of data processed. A Gateway Endpoint for S3 eliminates that cost entirely and improves security by keeping the traffic off the public internet.

Typical SAA scenario question: "An EC2 instance in a private subnet needs access to S3. Traffic must not traverse the public internet, and the solution must minimize cost." Answer: VPC Gateway Endpoint for S3.


Transit Gateway

Transit Gateway (TGW) is a managed network hub. Instead of a full mesh of VPC peering connections between N VPCs (which requires N*(N-1)/2 connections), each VPC attaches to the Transit Gateway. Any attached VPC can reach any other through the hub.

Transit Gateway also supports:
- VPN connections to on-premises networks
- Direct Connect gateway attachment for dedicated connectivity
- Transit Gateway peering between Regions for global connectivity
- Route tables per attachment — enabling you to control which VPCs can route to which, rather than allowing all-to-all connectivity

At enterprise scale — banks, large consulting firms, MSSPs — the standard AWS multi-account architecture uses a centralized network account that owns the Transit Gateway, a shared services VPC handles logging and monitoring, and business unit VPCs attach through TGW route tables. AWS Resource Access Manager (RAM) shares the Transit Gateway across accounts without requiring a peering mesh. This is the pattern underlying AWS Landing Zone and Control Tower reference architectures.


VPC Flow Logs

VPC Flow Logs capture metadata about IP traffic on network interfaces in your VPC. They do not capture packet contents. They capture: source IP, destination IP, source port, destination port, protocol, number of bytes, number of packets, action (ACCEPT or REJECT), and log status.

Flow Logs can be enabled at three levels: VPC level, subnet level, or individual ENI level. ENI level provides the most granular data.

Logs are delivered to CloudWatch Logs or S3. For ad hoc querying of S3-delivered logs at scale, use Amazon Athena. For real-time alerting on patterns in CloudWatch Logs, use CloudWatch Logs Insights with metric filters.

Security uses: detecting unusual outbound connections from private subnets, identifying port scanning behavior from internal resources, confirming whether a suspected data exfiltration connection actually occurred and how many bytes were transferred.

Compliance uses: SOC 2, PCI-DSS, and most enterprise security frameworks require network traffic logging. VPC Flow Logs are the AWS mechanism that satisfies this requirement.

Key distinction for the exam: CloudTrail captures API calls (who called which AWS API, when, from where). Flow Logs capture network traffic metadata (which IP connected to which IP on which port). They are complementary but entirely different.


Senior Engineer Insight

The most expensive VPC mistake in production is not a security misconfiguration — it is routing decisions that silently cost money every day. NAT Gateways are often provisioned for internet access and then become the default path for all outbound traffic, including S3 and DynamoDB. A Gateway Endpoint for S3 costs nothing and eliminates NAT Gateway data processing charges for S3 traffic. Before adding or expanding a NAT Gateway, always ask: which services do my private resources actually need to reach, and which of those could use an endpoint instead?

The second most common operational error: debugging Security Group rules for hours when the actual problem is a NACL. Security Groups are stateful and rarely cause subtle failures — if you forget a rule, traffic is just blocked in one direction. NACLs fail in more confusing ways because stateless behavior means traffic gets in but responses never get out, making the application appear to partially work.

---

REAL-WORLD PRACTICAL RELEVANCE

At a Canadian bank or large enterprise, cloud network architecture almost always follows a hub-and-spoke pattern: a centralized network account owns the Transit Gateway, a shared services VPC handles logging and monitoring, and business unit VPCs attach through TGW route tables. Security teams enforce NACLs at the subnet level as a secondary control layer on top of Security Groups. VPC Flow Logs feed into a SIEM (Splunk or Microsoft Sentinel) for continuous monitoring.

At an MSSP or SOC environment, VPC Flow Logs are treated as a primary data source for threat detection. Detection rules look for private instances initiating unexpected outbound connections, high byte-count flows to unknown external IPs, and REJECT patterns that suggest internal scanning.

For DevOps and platform engineers, the day-to-day work involves maintaining consistent VPC architecture in Terraform: managing CIDR blocks, endpoint policies, route table associations, and Security Group rules across environments. Mistakes in CIDR allocation create overlapping ranges that block future peering or TGW attachments.

---

INTERVIEW ANGLE

How this topic appears in interviews:

"Walk me through the difference between NACLs and Security Groups."
Strong answer: "Security Groups are stateful ENI-level firewalls — they only allow rules, and return traffic is automatically permitted. I use them for all standard access control between tiers: web servers, app servers, databases. NACLs are stateless subnet-level firewalls that support both allow and deny rules processed in order. I use NACLs specifically when I need to explicitly block a source IP, because Security Groups cannot deny. In incident response, a NACL deny rule is the fastest way to cut off a confirmed malicious source across all resources in a subnet."

"How would you connect 20 VPCs across three AWS accounts?"
Strong answer: "I would use Transit Gateway with Resource Access Manager to share the TGW across accounts. Each VPC attaches to the TGW rather than peering directly. I would configure TGW route tables to control which VPCs can communicate, rather than allowing all-to-all connectivity. For on-premises connectivity, I would attach the Direct Connect gateway to the same TGW rather than to each VPC separately."

"An EC2 instance in a private subnet is failing to reach S3. How do you troubleshoot?"
Strong answer: "First I check whether a Gateway Endpoint for S3 exists and whether it is added to the private subnet route table. If not, that is the fix and it is free. If there is no endpoint and no NAT Gateway, that is the root cause — the instance has no path to S3. If there is a NAT Gateway, I check the route table for the default route pointing to it. Then I check the Security Group on the instance and the endpoint policy. Finally, I enable Flow Logs on the subnet and look for REJECT entries on port 443 to confirm where the traffic is being dropped."

---

COMMON EXAM TRAPS AND MISCONCEPTIONS

Trap 1: Forgetting NACL stateless behavior for ephemeral ports. Inbound allow on port 80 does not mean responses will be allowed out. You must add an outbound rule allowing ephemeral ports (1024-65535) to the client CIDR. This is the most common NACL question on SAA.

Trap 2: Assuming VPC peering is transitive. It is not. Three-VPC chains do not route automatically through the middle VPC. This is tested directly.

Trap 3: Confusing Gateway Endpoints with Interface Endpoints. Gateway Endpoints are free and cover only S3 and DynamoDB. Interface Endpoints cost money per hour and cover all other services. The exam will present cost-optimization scenarios that require choosing the correct endpoint type.

Trap 4: Thinking Flow Logs capture packet contents. They capture metadata only. Flow Logs will tell you that a connection occurred and how many bytes transferred. They will not tell you what data was sent.

Trap 5: Assuming Security Groups can deny traffic. They cannot. If you need to block a specific source, you must use a NACL.

Trap 6: Confusing CloudTrail and Flow Logs. CloudTrail = API call logging. Flow Logs = network traffic metadata. A question about "who deleted an S3 bucket" points to CloudTrail. A question about "what IP addresses connected to my EC2 instance" points to Flow Logs.

---

MUST-KNOW TERMS

VPC — Virtual Private Cloud; an isolated, logically defined network in AWS where you launch and control resources with custom IP ranges, subnets, route tables, and gateways.

Security Group — A stateful, virtual firewall applied at the ENI level; supports allow rules only; return traffic is automatically permitted without explicit rules.

NACL — Network Access Control List; a stateless firewall applied at the subnet level; supports both allow and deny rules; evaluates rules in numerical order, stopping at the first match.

Stateful — A firewall behavior where return traffic for an allowed connection is automatically permitted without needing an explicit outbound rule.

Stateless — A firewall behavior where each direction of traffic (inbound and outbound) must be explicitly permitted; NACLs are stateless.

Ephemeral Ports — The dynamic, high-numbered port range (typically 1024-65535) used by clients to receive response traffic; must be explicitly allowed in NACL outbound rules.

VPC Peering — A networking connection between two VPCs enabling private communication through the AWS backbone; not transitive; cannot peer overlapping CIDRs.

VPC Gateway Endpoint — A free, route-table-based endpoint for accessing S3 or DynamoDB from within a VPC without using the public internet.

VPC Interface Endpoint (PrivateLink) — A per-hour-cost endpoint that creates a private ENI in your subnet for accessing most AWS services without traversing the public internet.

Transit Gateway (TGW) — A managed AWS network hub that connects multiple VPCs and on-premises networks, eliminating the need for a full mesh of peering connections.

VPC Flow Logs — A logging feature that captures metadata (source/destination IP, port, protocol, bytes, ACCEPT/REJECT) for network traffic on ENIs, subnets, or an entire VPC.

ENI — Elastic Network Interface; a virtual network card that can be attached to an instance or other resource within a VPC; the target of Security Group rules.

Bastion Host — A hardened EC2 instance in a public subnet used as a controlled jump server for SSH or RDP access to instances in private subnets.

Transit Gateway Route Table — A routing construct within TGW that controls which VPC attachments can send traffic to which destinations, enabling network segmentation at scale.

---

FREE STUDY RESOURCES

1. AWS VPC User Guide (official): docs.aws.amazon.com/vpc/latest/userguide/ — The authoritative reference for every VPC concept. Read the sections on Security Groups, NACLs, VPC Endpoints, and Flow Logs.

2. AWS Transit Gateway Documentation (official): docs.aws.amazon.com/vpc/latest/tgw/ — Covers TGW architecture, route tables, RAM sharing, and hybrid connectivity.

3. Adrian Cantrill SAA Course (learn.cantrill.io, $45 USD) — Referenced in your roadmap as non-negotiable. His VPC module is the most complete available for SAA.

4. AWS re:Invent VPC Deep Dive Sessions (YouTube) — Search "AWS re:Invent VPC Deep Dive" for talks by AWS networking engineers explaining production patterns. These go beyond exam level into real architecture decisions.

5. Tutorials Dojo SAA Practice Exams (tutorialsdojo.com) — Contains the highest density of VPC scenario questions aligned with the real SAA-C03 exam. Every wrong answer has a detailed explanation.

---

HANDS-ON TASK (30-60 minutes)

Build a multi-tier VPC manually in the AWS Free Tier. This replicates the lab in your roadmap.

Step 1: Create a VPC with a /16 CIDR block (for example, 10.0.0.0/16).
Step 2: Create a public subnet (/24) and a private subnet (/24) in the same Availability Zone.
Step 3: Create and attach an Internet Gateway to the VPC.
Step 4: Create a route table for the public subnet. Add a route: 0.0.0.0/0 pointing to the IGW. Associate this route table with the public subnet.
Step 5: Create a route table for the private subnet. It should have only the local route (10.0.0.0/16 local). Do not add an IGW route. Associate it with the private subnet.
Step 6: Create a Security Group allowing inbound SSH (port 22) from your IP only (/32 CIDR). Allow all outbound.
Step 7: Launch a t2.micro EC2 instance in the public subnet with a public IP. Verify you can SSH to it.
Step 8: Create a VPC Gateway Endpoint for S3. In the endpoint creation screen, select your private subnet route table. After creation, verify a new route entry (pl-xxxxxxxx) appears in the private subnet route table.
Step 9: Enable VPC Flow Logs at the VPC level. Deliver logs to CloudWatch Logs. Generate traffic (SSH to your EC2, attempt a connection that gets rejected). Then go to CloudWatch Logs and view the captured flow log entries. Identify ACCEPT and REJECT records.
Step 10: Delete all resources after the lab to avoid charges: terminate EC2, delete endpoints, delete route tables, delete subnets, detach and delete IGW, delete VPC.

Goal: After this lab, you should be able to see exactly how route tables control traffic paths, how the endpoint appears as a route entry, and what Flow Logs look like in practice.

---

CERTIFICATION-STYLE PRACTICE QUESTIONS

Question 1:
A company operates 15 VPCs across three AWS accounts. All VPCs need to communicate with each other and with an on-premises data center connected via AWS Direct Connect. The network team wants to minimize the number of connections to manage. Which solution best meets these requirements?

A) Create VPC peering connections between all 15 VPCs and connect each VPC to the Direct Connect gateway individually
B) Deploy a Transit Gateway in each of the three accounts and peer the Transit Gateways together using peering attachments
C) Deploy a single Transit Gateway, share it across accounts using AWS Resource Access Manager, and attach all VPCs and the Direct Connect gateway to it
D) Use VPC Interface Endpoints to connect the VPCs and deploy a separate VPN connection from each VPC to on-premises


Question 2:
An EC2 instance running in a private subnet must access objects in Amazon S3. The security team requires that traffic must never traverse the public internet, and the chosen solution must not incur any per-hour or per-request charges from the networking component. What is the correct solution?

A) Create a NAT Gateway in the public subnet and add a default route in the private subnet route table pointing to it
B) Create a VPC Interface Endpoint for S3 in the private subnet
C) Attach an Internet Gateway to the VPC and add a 0.0.0.0/0 route in the private subnet route table
D) Create a VPC Gateway Endpoint for S3 and add the endpoint route to the private subnet route table


Question 3:
A solutions architect has configured a NACL on a public subnet hosting web servers. Inbound rule 100 allows TCP traffic on port 443 from 0.0.0.0/0. Users report that HTTPS connections are being established but responses never arrive. No Security Group rules were changed. What is the most likely cause?

A) The Security Group on the web servers does not allow outbound traffic on port 443
B) The NACL does not have an outbound rule allowing TCP traffic on ephemeral ports (1024-65535) to 0.0.0.0/0
C) Internet Gateways block outbound HTTPS traffic by default until explicitly permitted
D) NACLs only support traffic filtering for UDP protocols, not TCP


Question 4:
A company has three VPCs in the same Region: VPC-A, VPC-B, and VPC-C. VPC-A has a peering connection to VPC-B, and VPC-B has a peering connection to VPC-C. An engineer attempts to connect from a resource in VPC-A to a resource in VPC-C but the connection fails. The route tables are correctly updated for the A-to-B and B-to-C connections. Why is the connection failing?

A) VPC peering does not support traffic between VPCs in the same AWS Region
B) Route table entries for peering connections expire after 24 hours and must be renewed
C) VPC peering is not transitive; VPC-A cannot route traffic to VPC-C through VPC-B
D) VPC peering requires both VPCs to be in the same account before cross-VPC routing is permitted


Question 5:
A security engineer needs to investigate whether a compromised EC2 instance in a private subnet made any outbound connections to external IP addresses during the previous 48 hours. The engineer needs to see source IP, destination IP, destination port, and whether the connection was allowed or rejected. Which AWS service provides this data?

A) AWS CloudTrail
B) AWS GuardDuty
C) VPC Flow Logs
D) AWS Config

---

ANSWER KEY

Question 1: C
Transit Gateway with Resource Access Manager (RAM) sharing is the correct answer for connecting multiple VPCs across accounts to a shared hub and to Direct Connect at scale. A single TGW attached to all 15 VPCs and the Direct Connect gateway requires only 16 total attachments (15 VPCs + 1 DX) rather than the 105 peering connections a full mesh would require. Option A requires a full mesh of peering connections and individual Direct Connect gateway attachments, creating massive operational overhead. Option B introduces three separate TGWs when one shared TGW solves the problem. Option D is incorrect because Interface Endpoints connect to AWS services, not to other VPCs, and per-VPC VPNs do not scale.

Question 2: D
A VPC Gateway Endpoint for S3 is free, routes traffic through the AWS backbone (never the public internet), and integrates via a route table entry rather than an ENI with hourly charges. Option A (NAT Gateway) routes traffic to the public internet, violating the security requirement. Option B (Interface Endpoint for S3) routes traffic privately but incurs per-hour charges, violating the cost requirement. Interface Endpoints for S3 exist but Gateway Endpoints are the cost-optimal and security-compliant choice for this exact scenario. Option C (Internet Gateway in private subnet) does not work because resources in private subnets do not have public IP addresses and cannot use an IGW directly.

Question 3: B
NACLs are stateless. Inbound rule 100 allows connections arriving on port 443. However, the server's responses leave on ephemeral ports (1024-65535), not port 443. Without an outbound NACL rule allowing ephemeral ports to 0.0.0.0/0, those response packets are dropped by the NACL. Security Groups (Option A) are stateful and automatically allow return traffic, so they are not the cause. Internet Gateways (Option C) do not filter traffic by port. NACLs (Option D) fully support TCP — this is a fabricated distractor.

Question 4: C
VPC peering is explicitly non-transitive. AWS does not route traffic through an intermediate VPC to reach a third VPC. If VPC-A needs to reach VPC-C, there must be a direct peering connection between A and C, or the architecture must be redesigned to use Transit Gateway. Option A is incorrect — peering within the same Region is fully supported. Option B is fabricated — peering routes do not expire. Option D is incorrect — cross-account peering is supported.

Question 5: C
VPC Flow Logs capture the exact metadata required: source IP, destination IP, destination port, protocol, byte count, and ACCEPT or REJECT status. This is precisely what Flow Logs are designed for. CloudTrail (Option A) records API calls to AWS services, not network-level IP traffic between instances and external addresses. GuardDuty (Option B) produces threat findings derived from multiple data sources including Flow Logs, but does not give the engineer direct access to raw connection records. AWS Config (Option D) tracks changes to resource configurations and does not log network traffic.

---

TODAY'S CHECKLIST

[ ] Study NACLs vs Security Groups until you can explain the stateful vs stateless distinction, ephemeral port behavior, and the correct use case for each without looking at notes.

[ ] Complete the hands-on VPC lab: build a multi-tier VPC with public and private subnets, route tables, a Gateway Endpoint for S3, and enable Flow Logs; view at least one ACCEPT and one REJECT entry in CloudWatch Logs.

[ ] Complete at least one Tutorials Dojo SAA practice exam set with a focus on networking questions; review every wrong answer and write down the reason each distractor is incorrect.
