# Amazon EKS User Guide

-----
*****Copyright &copy; Amazon Web Services, Inc. and/or its affiliates. All rights reserved.*****

-----
Amazon's trademarks and trade dress may not be used in
connection with any product or service that is not Amazon's,
in any manner that is likely to cause confusion among customers,
or in any manner that disparages or discredits Amazon. All other
trademarks not owned by Amazon are the property of their respective
owners, who may or may not be affiliated with, connected to, or
sponsored by Amazon.

-----
## Contents
+ [What is Amazon EKS?](what-is-eks.md)
   + [Common use cases in Amazon EKS](common-use-cases.md)
   + [Amazon EKS architecture](eks-architecture.md)
   + [Kubernetes concepts](kubernetes-concepts.md)
   + [Deployment options](eks-deployment-options.md)
+ [Set up to use Amazon EKS](setting-up.md)
   + [Set up AWS CLI](install-awscli.md)
   + [Set up kubectl and eksctl](install-kubectl.md)
+ [Quickstart: Deploy a web app and store data](quickstart.md)
+ [Get started with Amazon EKS](getting-started.md)
   + [Getting started with Amazon EKS – eksctl](getting-started-eksctl.md)
   + [Getting started with Amazon EKS – AWS Management Console and AWS CLI](getting-started-console.md)
   + [Learn Amazon EKS by example](learn-eks.md)
+ [Amazon EKS clusters](clusters.md)
   + [Create an Amazon EKS cluster](create-cluster.md)
   + [Prepare for Kubernetes version upgrades with cluster insights](cluster-insights.md)
   + [Update existing cluster to new Kubernetes version](update-cluster.md)
   + [Delete a cluster](delete-cluster.md)
   + [Control network access to cluster API server endpoint](cluster-endpoint.md)
   + [Encrypt Kubernetes secrets with AWS KMS on existing clusters](enable-kms.md)
   + [Deploy Windows nodes on EKS clusters](windows-support.md)
   + [Disable Windows support](disable-windows-support.md)
   + [Legacy cluster support for Windows nodes](legacy-windows-support.md)
   + [Deploy private clusters with limited internet access](private-clusters.md)
   + [Understand the Kubernetes version lifecycle on EKS](kubernetes-versions.md)
      + [Review release notes for Kubernetes versions on standard support](kubernetes-versions-standard.md)
      + [Review release notes for Kubernetes versions on extended support](kubernetes-versions-extended.md)
      + [Review release notes for Kubernetes version 1.22](kubernetes-versions-1-21-1-22.md)
      + [Manage EKS extended support](extended-support-control.md)
   + [View Amazon EKS platform versions for each Kubernetes version](platform-versions.md)
   + [Scale cluster compute with Karpenter and Cluster Autoscaler](autoscaling.md)
+ [Manage access](cluster-auth.md)
   + [Grant IAM users and roles access to Kubernetes APIs](grant-k8s-access.md)
      + [Grant IAM users access to Kubernetes with EKS access entries](access-entries.md)
         + [Change authentication mode to use access entries](setting-up-access-entries.md)
         + [Create access entries](creating-access-entries.md)
         + [Update access entries](updating-access-entries.md)
         + [Delete access entries](deleting-access-entries.md)
      + [Associating and disassociating access policies to and from access entries](access-policies.md)
      + [Migrating existing aws-auth ConfigMap entries to access entries](migrating-access-entries.md)
      + [Grant IAM users access to Kubernetes with a ConfigMap](auth-configmap.md)
      + [Grant users access to Kubernetes with an external OIDC provider](authenticate-oidc-identity-provider.md)
   + [Connect kubectl to an EKS cluster by creating a kubeconfig file](create-kubeconfig.md)
   + [Grant Kubernetes workloads access to AWS using Kubernetes Service Accounts](service-accounts.md)
      + [Learn how EKS Pod Identity grants pods access to AWS services](pod-identities.md)
         + [Understand how EKS Pod Identity works](pod-id-how-it-works.md)
         + [Set up the Amazon EKS Pod Identity Agent](pod-id-agent-setup.md)
         + [Assign an IAM role to a Kubernetes service account](pod-id-association.md)
         + [Configure pods to access AWS services with service accounts](pod-id-configure-pods.md)
         + [Grant pods access to AWS resources based on tags](pod-id-abac.md)
         + [Use a supported AWS SDK](pod-id-minimum-sdk.md)
         + [Create IAM role with trust policy required by EKS Pod Identity](pod-id-role.md)
      + [IAM roles for service accounts](iam-roles-for-service-accounts.md)
         + [Create an IAM OIDC provider for your cluster](enable-iam-roles-for-service-accounts.md)
         + [Assign IAM roles to Kubernetes service accounts](associate-service-account-role.md)
         + [Configure Pods to use a Kubernetes service account](pod-configuration.md)
         + [Configure the AWS Security Token Service endpoint for a service account](configure-sts-endpoint.md)
         + [Cross-account IAM permissions](cross-account-access.md)
         + [Using a supported AWS SDK](iam-roles-for-service-accounts-minimum-sdk.md)
         + [Fetch signing keys to validate OIDC tokens](irsa-fetch-keys.md)
+ [Amazon EKS nodes](eks-compute.md)
   + [Managed node groups](managed-node-groups.md)
      + [Creating a managed node group](create-managed-node-group.md)
         + [Create a managed node group with Amazon EC2 Capacity Blocks for ML](capacity-blocks-mng.md)
      + [Updating a managed node group](update-managed-node-group.md)
         + [Managed node update behavior](managed-node-update-behavior.md)
      + [Node taints on managed node groups](node-taints-managed-node-groups.md)
      + [Customizing managed nodes with launch templates](launch-templates.md)
      + [Deleting a managed node group](delete-managed-node-group.md)
   + [Self-managed nodes](worker.md)
      + [Launching self-managed Amazon Linux nodes](launch-workers.md)
         + [Use Capacity Blocks for ML with self-managed nodes](capacity-blocks.md)
      + [Launching self-managed Bottlerocket nodes](launch-node-bottlerocket.md)
      + [Launching self-managed Windows nodes](launch-windows-workers.md)
      + [Launching self-managed Ubuntu nodes](launch-node-ubuntu.md)
      + [Self-managed node updates](update-workers.md)
         + [Migrating to a new node group](migrate-stack.md)
         + [Updating an existing self-managed node group](update-stack.md)
   + [AWS Fargate](fargate.md)
      + [Getting started with AWS Fargate using Amazon EKS](fargate-getting-started.md)
      + [AWS Fargate profile](fargate-profile.md)
      + [Fargate Pod configuration](fargate-pod-configuration.md)
      + [Fargate OS patching](fargate-pod-patching.md)
      + [Fargate metrics](monitoring-fargate-usage.md)
      + [Fargate logging](fargate-logging.md)
   + [Choosing an Amazon EC2 instance type](choosing-instance-type.md)
   + [Amazon EKS optimized AMIs](eks-optimized-amis.md)
      + [Amazon EKS ended support for Dockershim](dockershim-deprecation.md)
      + [Amazon EKS optimized Amazon Linux AMIs](eks-optimized-ami.md)
         + [Amazon EKS optimized Amazon Linux AMI versions](eks-linux-ami-versions.md)
         + [Retrieving Amazon EKS optimized Amazon Linux AMI IDs](retrieve-ami-id.md)
         + [Amazon EKS optimized Amazon Linux AMI build script](eks-ami-build-scripts.md)
            + [Configuring VT1 for your custom Amazon Linux AMI](vt1.md)
            + [Configuring DL1 for your custom Amazon Linux 2 AMI](dl1.md)
      + [Amazon EKS optimized Bottlerocket AMIs](eks-optimized-ami-bottlerocket.md)
         + [Amazon EKS optimized Bottlerocket AMI versions](eks-ami-versions-bottlerocket.md)
         + [Retrieving Amazon EKS optimized Bottlerocket AMI IDs](retrieve-ami-id-bottlerocket.md)
         + [Bottlerocket compliance support](bottlerocket-compliance-support.md)
      + [Amazon EKS optimized Ubuntu Linux AMIs](eks-partner-amis.md)
      + [Amazon EKS optimized Windows AMIs](eks-optimized-windows-ami.md)
         + [Amazon EKS optimized Windows AMI versions](eks-ami-versions-windows.md)
         + [Retrieving Amazon EKS optimized Windows AMI IDs](retrieve-windows-ami-id.md)
         + [Creating custom Amazon EKS optimized Windows AMIs](eks-custom-ami-windows.md)
+ [Store application data](storage.md)
   + [Use Amazon EBS storage](ebs-csi.md)
      + [Create an Amazon EBS CSI driver IAM role](csi-iam-role.md)
      + [Manage the Amazon EBS CSI driver as an Amazon EKS add-on](managing-ebs-csi.md)
      + [Deploy a sample application](ebs-sample-app.md)
      + [Amazon EBS CSI migration frequently asked questions](ebs-csi-migration-faq.md)
   + [Use Amazon EFS storage](efs-csi.md)
   + [Use Amazon FSx for Lustre storage](fsx-csi.md)
   + [Use Amazon FSx for NetApp ONTAP storage](fsx-ontap.md)
   + [Use Amazon FSx for OpenZFS storage](fsx-openzfs-csi.md)
   + [Use Amazon File Cache](file-cache-csi.md)
   + [Use Mountpoint for Amazon S3 storage](s3-csi.md)
   + [Use snapshot controller with CSI storage](csi-snapshot-controller.md)
+ [Amazon EKS networking](eks-networking.md)
   + [Amazon EKS VPC and subnet requirements and considerations](network_reqs.md)
   + [Creating a VPC for your Amazon EKS cluster](creating-a-vpc.md)
   + [Amazon EKS security group requirements and considerations](sec-group-reqs.md)
   + [Amazon EKS networking add-ons](eks-networking-add-ons.md)
      + [Working with the Amazon VPC CNI plugin for Kubernetes Amazon EKS add-on](managing-vpc-cni.md)
         + [Configuring the Amazon VPC CNI plugin for Kubernetes to use IAM roles for service accounts (IRSA)](cni-iam-role.md)
         + [Choosing Pod networking use cases](pod-networking-use-cases.md)
            + [IPv6 addresses for clusters, Pods, and services](cni-ipv6.md)
            + [SNAT for Pods](external-snat.md)
            + [Configure your cluster for Kubernetes network policies](cni-network-policy.md)
            + [Custom networking for pods](cni-custom-network.md)
            + [Increase the amount of available IP addresses for your Amazon EC2 nodes](cni-increase-ip-addresses.md)
            + [Security groups for Pods](security-groups-for-pods.md)
            + [Multiple network interfaces for Pods](pod-multiple-network-interfaces.md)
         + [Alternate compatible CNI plugins](alternate-cni-plugins.md)
      + [What is the AWS Load Balancer Controller?](aws-load-balancer-controller.md)
         + [Install the AWS Load Balancer Controller using Helm](lbc-helm.md)
         + [Install the AWS Load Balancer Controller add-on using Kubernetes Manifests](lbc-manifest.md)
         + [Migrate from Deprecated Controller](lbc-remove.md)
      + [Working with the CoreDNS Amazon EKS add-on](managing-coredns.md)
         + [Autoscaling CoreDNS](coredns-autoscaling.md)
         + [CoreDNS metrics](coredns-metrics.md)
      + [Working with the Kubernetes kube-proxy add-on](managing-kube-proxy.md)
   + [Access the Amazon Elastic Kubernetes Service using an interface endpoint (AWS PrivateLink)](vpc-interface-endpoints.md)
+ [Workloads](eks-workloads.md)
   + [Deploy a sample application](sample-deployment.md)
   + [Adjust pod resources with Vertical Pod Autoscaler](vertical-pod-autoscaler.md)
   + [Scale pod deployments with Horizontal Pod Autoscaler](horizontal-pod-autoscaler.md)
   + [Route TCP and UDP traffic with Network Load Balancers](network-load-balancing.md)
   + [Route application and HTTP traffic with Application Load Balancers](alb-ingress.md)
   + [Restricting external IP addresses that can be assigned to services](restrict-service-external-ip.md)
   + [Copy a container image from one repository to another repository](copy-image-to-repository.md)
   + [Amazon container image registries](add-ons-images.md)
   + [Amazon EKS add-ons](eks-add-ons.md)
      + [Available Amazon EKS add-ons from AWS](workloads-add-ons-available-eks.md)
         + [Amazon VPC CNI plugin for Kubernetes](add-ons-vpc-cni.md)
         + [CoreDNS](add-ons-coredns.md)
         + [Kube-proxy](add-ons-kube-proxy.md)
         + [Amazon EBS CSI driver](add-ons-aws-ebs-csi-driver.md)
         + [Amazon EFS CSI driver](add-ons-aws-efs-csi-driver.md)
         + [Mountpoint for Amazon S3 CSI Driver](mountpoint-for-s3-add-on.md)
         + [CSI snapshot controller](addons-csi-snapshot-controller.md)
         + [AWS Distro for OpenTelemetry](add-ons-adot.md)
         + [Amazon GuardDuty agent](add-ons-guard-duty.md)
         + [Amazon CloudWatch Observability agent](amazon-cloudwatch-observability.md)
         + [EKS Pod Identity Agent](add-ons-pod-id.md)
      + [Additional Amazon EKS add-ons from independent software vendors](workloads-add-ons-available-vendors.md)
         + [Accuknox](add-on-accuknox.md)
         + [Akuity](add-on-akuity.md)
         + [Calyptia](add-on-calyptia.md)
         + [Cisco Observability Collector](add-on-cisco-collector.md)
         + [Cisco Observability Operator](add-on-cisco-operator.md)
         + [CLOUDSOFT](add-on-CLOUDSOFT.md)
         + [Cribl](add-on-cribl.md)
         + [Dynatrace](add-on-dynatrace.md)
         + [Datree](add-on-datree-pro.md)
         + [Datadog](add-on-datadog.md)
         + [Groundcover](add-on-groundcover.md)
         + [Grafana Labs](add-on-grafana.md)
         + [Guance](add-on-GUANCE.md)
         + [HA Proxy](add-on-ha-proxy.md)
         + [Kpow](add-on-kpow.md)
         + [Kubecost](add-on-kubecost.md)
         + [Kasten](add-on-kasten.md)
         + [Kong](add-on-kong.md)
         + [LeakSignal](add-on-leaksignal.md)
         + [NetApp](add-on-netapp.md)
         + [New Relic](add-on-new-relic.md)
         + [Rafay](add-on-rafay.md)
         + [Rad Security](add-on-RAD.md)
         + [SolarWinds](add-on-solarwinds.md)
         + [Solo](add-on-solo.md)
         + [Snyk](add-on-snyk.md)
         + [Stormforge](add-on-stormforge.md)
         + [Splunk](add-on-splunk.md)
         + [Teleport](add-on-teleport.md)
         + [Tetrate](add-on-tetrate.md)
         + [Upbound Universal Crossplane](add-on-upbound.md)
         + [Upwind](add-on-upwind.md)
      + [Creating an Amazon EKS add-on](creating-an-add-on.md)
      + [Updating an Amazon EKS add-on](updating-an-add-on.md)
      + [Verifying Amazon EKS add-on version compatibility with a cluster](addon-compat.md)
      + [Removing an Amazon EKS add-on from a cluster](removing-an-add-on.md)
      + [Determine fields you can customize for Amazon EKS add-ons](kubernetes-field-management.md)
      + [IAM roles for Amazon EKS add-ons](add-ons-iam.md)
         + [Retrieve IAM information about an Amazon EKS add-on](retreive-iam-info.md)
         + [Use Pod Identities to assign an IAM role to an Amazon EKS add-on](update-addon-role.md)
         + [Remove Pod Identity associations from an Amazon EKS add-on](remove-addon-role.md)
         + [Troubleshoot Pod Identities for EKS add-ons](addon-id-troubleshoot.md)
   + [Validate container image signatures during deployment](image-verification.md)
   + [Run machine learning training on Amazon EKS with Elastic Fabric Adapter](node-efa.md)
   + [Deploy ML inference workloads with AWSInferentia on Amazon EKS](inferentia-support.md)
+ [Cluster management](eks-managing.md)
   + [Monitor and optimize Amazon EKS cluster costs](cost-monitoring.md)
   + [View resource usage with the KubernetesMetrics Server](metrics-server.md)
   + [Deploy applications with Helm on Amazon EKS](helm.md)
   + [Organize Amazon EKS resources with tags](eks-using-tags.md)
   + [View and manage Amazon EKS and Fargate service quotas](service-quotas.md)
+ [Security in Amazon EKS](security.md)
   + [Certificate signing](cert-signing.md)
   + [Identity and access management for Amazon EKS](security-iam.md)
      + [How Amazon EKS works with IAM](security_iam_service-with-iam.md)
      + [Amazon EKS identity-based policy examples](security_iam_id-based-policy-examples.md)
      + [Using service-linked roles for Amazon EKS](using-service-linked-roles.md)
         + [Using roles for Amazon EKS clusters](using-service-linked-roles-eks.md)
         + [Using roles for Amazon EKS node groups](using-service-linked-roles-eks-nodegroups.md)
         + [Using roles for Amazon EKS Fargate profiles](using-service-linked-roles-eks-fargate.md)
         + [Using roles to connect a Kubernetes cluster to Amazon EKS](using-service-linked-roles-eks-connector.md)
         + [Using roles for Amazon EKS local clusters on Outpost](using-service-linked-roles-eks-outpost.md)
      + [Amazon EKS cluster IAM role](service_IAM_role.md)
      + [Amazon EKS node IAM role](create-node-role.md)
      + [Amazon EKS Pod execution IAM role](pod-execution-role.md)
      + [Amazon EKS connector IAM role](connector_IAM_role.md)
      + [AWS managed policies for Amazon Elastic Kubernetes Service](security-iam-awsmanpol.md)
      + [Troubleshooting IAM](security_iam_troubleshoot.md)
      + [Default Amazon EKS created Kubernetes roles and users](default-roles-users.md)
   + [Compliance validation for Amazon Elastic Kubernetes Service](compliance.md)
   + [Resilience in Amazon EKS](disaster-recovery-resiliency.md)
   + [Infrastructure security in Amazon EKS](infrastructure-security.md)
   + [Configuration and vulnerability analysis in Amazon EKS](configuration-vulnerability-analysis.md)
   + [Security best practices for Amazon EKS](security-best-practices.md)
   + [Pod security policy](pod-security-policy.md)
   + [Pod security policy (PSP) removal FAQ](pod-security-policy-removal-faq.md)
   + [Using AWS Secrets Manager secrets with Kubernetes](manage-secrets.md)
   + [Amazon EKS Connector considerations](security-connector.md)
+ [View Kubernetes resources](view-kubernetes-resources.md)
+ [Observability in Amazon EKS](eks-observe.md)
   + [Prometheus metrics](prometheus.md)
   + [Amazon EKS add-on support for Amazon CloudWatch](cloudwatch.md)
   + [Amazon EKS control plane logging](control-plane-logs.md)
   + [Logging Amazon EKS API calls with AWS CloudTrail](logging-using-cloudtrail.md)
      + [Amazon EKS information in CloudTrail](service-name-info-in-cloudtrail.md)
      + [Understanding Amazon EKS log file entries](understanding-service-name-entries.md)
      + [Auto Scaling group metrics collection](enable-asg-metrics.md)
   + [Amazon EKS add-on support for ADOT Operator](opentelemetry.md)
+ [More AWS services integrated with Amazon EKS](eks-integrations.md)
   + [Creating Amazon EKS resources with AWS CloudFormation](creating-resources-with-cloudformation.md)
   + [Amazon EKS and AWS Local Zones](local-zones.md)
   + [Deep Learning Containers](deep-learning-containers.md)
   + [Amazon VPC Lattice](integration-vpc-lattice.md)
   + [AWS Resilience Hub](integration-resilience-hub.md)
   + [Detect threats with Amazon GuardDuty](integration-guardduty.md)
   + [Using Amazon Security Lake with Amazon EKS](integration-securitylake.md)
   + [Amazon Detective](integration-detective.md)
+ [Amazon EKS troubleshooting](troubleshooting.md)
+ [Amazon EKS Connector](eks-connector.md)
   + [Connecting an external cluster](connecting-cluster.md)
   + [Granting access to an IAM principal to view Kubernetes resources on a cluster](connector-grant-access.md)
   + [Deregistering a cluster](deregister-connected-cluster.md)
   + [Troubleshooting issues in Amazon EKS Connector](troubleshooting-connector.md)
   + [Frequently asked questions](tsc-faq.md)
+ [Amazon EKS on AWS Outposts](eks-outposts.md)
   + [Local clusters for Amazon EKS on AWS Outposts](eks-outposts-local-cluster-overview.md)
      + [Creating a local cluster on an Outpost](eks-outposts-local-cluster-create.md)
      + [Amazon EKS local cluster platform versions](eks-outposts-platform-versions.md)
      + [Amazon EKS local cluster VPC and subnet requirements and considerations](eks-outposts-vpc-subnet-requirements.md)
      + [Preparing for network disconnects](eks-outposts-network-disconnects.md)
      + [Capacity considerations](eks-outposts-capacity-considerations.md)
      + [Troubleshooting local clusters for Amazon EKS on AWS Outposts](eks-outposts-troubleshooting.md)
   + [Launching self-managed Amazon Linux nodes on an Outpost](eks-outposts-self-managed-nodes.md)
+ [Related projects](related-projects.md)
+ [Amazon EKS new features and roadmap](roadmap.md)
+ [Document history for Amazon EKS](doc-history.md)