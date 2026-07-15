**Good morning,**

My name is Vipin Kumar. I have 13 years of overall IT experience, with the last 5 years focused on Cloud and DevOps Engineering.

Currently, I am working as a DevOps Engineer, responsible for designing, automating, and managing cloud infrastructure on AWS. My day-to-day responsibilities include provisioning infrastructure using Terraform, managing Amazon EKS clusters, creating CI/CD pipelines using Jenkins, implementing GitOps using Argo CD, and containerizing applications with Docker.

In my current project, we deploy a three-tier banking application consisting of a frontend, backend, and database. Our CI/CD pipeline starts when developers push code to GitHub. Jenkins is triggered automatically through a webhook, builds the application, performs security scanning using Trivy, creates the Docker image, pushes it to Amazon ECR, and updates the deployment manifests. Argo CD then synchronizes the changes and deploys the application to the EKS cluster.

I also work with AWS services such as VPC, EC2, IAM, S3, ECR, ALB, Route 53, and CloudWatch. For monitoring and observability, we use Prometheus and Grafana. I actively support production by troubleshooting infrastructure and application issues, ensuring high availability and smooth deployments.

I closely collaborate with developers, QA teams, and application owners to ensure reliable deployments across development, staging, and production environments.

I am now looking for an opportunity where I can contribute my DevOps expertise while growing further as an AI Platform Engineer.


Friday 5:47 PM

For 8–12 years of experience, interviewers often move beyond definitions and ask advanced architecture, troubleshooting, and real-world scenario questions. Below are 50 more interview questions (91–140) with concise answers.

AWS Advanced
91. What happens when you launch an EC2 instance?

Answer:

AMI is selected.
VPC and subnet are chosen.
ENI (Elastic Network Interface) is attached.
Security Group is attached.
EBS volume is attached.
IAM Role is attached (optional).
Instance boots using the hypervisor.
User Data script executes (if configured).
92. What is an AMI?

An Amazon Machine Image (AMI) is a template containing:

Operating System
Application software
Configuration
Permissions

It is used to launch EC2 instances consistently.

93. Explain the EC2 boot process.

BIOS/UEFI → Hypervisor → Kernel → Operating System → Cloud-Init/User Data → Application Startup.

94. Difference between EBS and Instance Store?
EBS	Instance Store
Persistent	Temporary
Network-attached	Physically attached
Snapshots supported	No snapshots
Recommended for production	Suitable for temporary/cache data
95. What is an Elastic IP?

A static public IPv4 address that can be remapped to another EC2 instance.

96. What is CloudFormation Drift Detection?

It identifies differences between the deployed infrastructure and the CloudFormation template.

97. What is Terraform Drift?

Terraform detects infrastructure changes made outside Terraform by comparing the current infrastructure with the Terraform state during terraform plan.

98. What are Terraform Workspaces?

Workspaces allow managing multiple environments (e.g., dev, test, prod) using the same Terraform configuration while maintaining separate state files.

99. Explain Terraform Lifecycle Meta-Arguments.

Examples include:

lifecycle {
  create_before_destroy = true
  prevent_destroy       = true
  ignore_changes        = [tags]
}
100. What are Terraform Data Sources?

Data sources allow Terraform to read information about existing infrastructure without creating it.

Example:

data "aws_vpc" "default" {}
Kubernetes Advanced
101. Explain the Kubernetes Control Plane.

Components:

API Server
Scheduler
Controller Manager
etcd

The Control Plane manages the cluster state.

102. What is etcd?

A distributed key-value database used by Kubernetes to store cluster configuration and state.

103. What is kubelet?

An agent running on every worker node that communicates with the API Server and ensures containers are running as expected.

104. What is kube-proxy?

It manages network rules and enables communication between Services and Pods.

105. What is CoreDNS?

CoreDNS provides internal DNS resolution for Kubernetes services.

Example:

backend.default.svc.cluster.local
106. What is a DaemonSet?

A DaemonSet ensures one pod runs on every node.

Common examples:

Fluent Bit
Prometheus Node Exporter
Security agents
107. What is a Job?

Runs a task until it completes successfully.

Example:

Database migration
Data import
108. What is a CronJob?

Runs Jobs on a schedule.

Example:

Every day at 2 AM
109. What is a ServiceAccount?

A Kubernetes identity used by Pods to interact with the Kubernetes API securely.

110. What is a Network Policy?

A Network Policy controls which Pods can communicate with other Pods or external services.

Docker Advanced
111. How do you reduce Docker image size?
Use Alpine-based images.
Use multi-stage builds.
Remove unnecessary packages.
Combine RUN commands.
Clean package caches.
112. What is the difference between CMD and ENTRYPOINT?
CMD	ENTRYPOINT
Default command	Main executable
Can be overridden	Typically fixed
113. What happens during docker build?
Docker reads the Dockerfile.
Executes each instruction in order.
Creates image layers.
Caches reusable layers.
Produces the final image.
114. Explain Docker Layer Caching.

Docker reuses unchanged layers from previous builds to speed up image creation.

115. What is Docker Compose?

Docker Compose manages multi-container applications using a docker-compose.yml file.

Git Advanced
116. Difference between Git Fetch and Git Pull?
Fetch	Pull
Downloads changes only	Downloads and merges changes
117. What is Git Reset?

git reset moves the branch pointer and can unstage or discard changes depending on the mode (--soft, --mixed, --hard).

118. What is Git Revert?

Creates a new commit that reverses the changes introduced by a previous commit without rewriting history.

Jenkins
119. Declarative vs Scripted Pipeline?
Declarative	Scripted
Simpler syntax	More flexible
Easier maintenance	More control
120. What are Jenkins Agents?

Agents execute build jobs assigned by the Jenkins Controller.

GitHub Actions
121. What are GitHub Runners?

Runners are machines that execute GitHub Actions workflows. They can be GitHub-hosted or self-hosted.

122. What are GitHub Secrets?

Encrypted values used to store sensitive information such as AWS credentials, API keys, and tokens.

Ansible
123. What is Idempotency in Ansible?

Running the same playbook multiple times results in the same desired state without making unnecessary changes.

124. What are Ansible Roles?

Roles organize playbooks into reusable components with directories for tasks, handlers, templates, files, and variables.

Python
125. Why use Boto3?

Boto3 is the AWS SDK for Python, used to automate AWS services such as EC2, S3, IAM, and Lambda.

126. How do you handle exceptions in Python?
try:
    print("Process")
except Exception as e:
    print(e)
Monitoring
127. Explain Prometheus Architecture.

Prometheus periodically scrapes metrics from configured targets, stores them in a time-series database, and allows querying with PromQL. Grafana visualizes these metrics.

128. What is Grafana?

Grafana is a visualization platform used to create dashboards for metrics, logs, and alerts.

129. Difference between Prometheus and CloudWatch?
Prometheus	CloudWatch
Open source	AWS managed
Pull-based	Native AWS monitoring
PromQL	CloudWatch Metrics
Security
130. How do you secure Kubernetes?
RBAC
Network Policies
Pod Security Standards
Secret management
Image scanning (Trivy)
Regular upgrades
Audit logging
131. How do you secure Docker images?
Use trusted base images.
Scan images with Trivy.
Remove unnecessary packages.
Avoid running containers as root.
Sign images where appropriate.
132. Explain Principle of Least Privilege.

Grant only the minimum permissions required to perform a task.

Scenario Questions
133. A Pod is Pending. How do you troubleshoot?

Check:

Available nodes
Resource requests
Node taints
PVC binding
Scheduler events

Command:

kubectl describe pod <pod-name>
134. Nodes are NotReady. What will you check?
Node health
kubelet status
Network connectivity
Disk space
CPU and memory
Cloud provider status
135. Deployment stuck in Progressing. What will you do?
Review rollout status.
Check ReplicaSets.
Review pod events and logs.
Verify readiness probes.
Roll back if necessary.
136. Jenkins pipeline suddenly fails. What is your approach?
Review pipeline logs.
Identify the failed stage.
Check credentials.
Verify external dependencies.
Test manually if needed.
Fix and rerun.
137. High latency after deployment. What will you do?
Compare with previous release.
Check application logs.
Review CPU and memory.
Analyze database performance.
Roll back if required.
138. How do you perform Root Cause Analysis (RCA)?
Collect logs and metrics.
Identify the triggering event.
Determine the root cause.
Implement a fix.
Add preventive measures.
Document findings and lessons learned.
139. How do you handle a Sev-1 Production Incident?
Acknowledge the incident immediately.
Assemble the response team.
Restore service as quickly as possible.
Keep stakeholders updated.
Collect evidence during the incident.
Conduct a post-incident RCA and implement preventive actions.
