# **Lab 6: Cloud Resource Comparison Across AWS, Azure, and Google Cloud**

**Name:** Ken Biju Jacob  
**Student ID:** 041171140  

---

## **Cloud Resource Descriptions and Comparison Table**

| # | Description | AWS (Service Name) | Azure (Service Name) | Google Cloud (Service Name) |
|---|--------------|--------------------|-----------------------|------------------------------|
| 1 | A compute service that provides scalable virtual machines for running applications. | Amazon EC2 | Azure Virtual Machine | Compute Engine |
| 2 | An object storage service used to store and retrieve data, commonly used for backups and static website content. | Amazon S3 | Azure Blob Storage | Cloud Storage |
| 3 | A managed relational database service that supports multiple database engines like MySQL, PostgreSQL, and SQL Server. | Amazon RDS | Azure Database for MySQL/SQL Server | Cloud SQL |
| 4 | A serverless compute service that allows you to run code in response to events without provisioning or managing servers. | AWS Lambda | Azure Functions | Cloud Functions |
| 5 | A virtual private network service that allows you to create isolated networks within the cloud provider's infrastructure. | Amazon VPC | Azure Virtual Network | Virtual Private Cloud (VPC) |
| 6 | A content delivery network (CDN) service that delivers data, videos, applications, and APIs to customers around the world with low latency. | Amazon CloudFront | Azure CDN | Cloud CDN |
| 7 | A managed NoSQL database service designed for low-latency, high-scale applications. | Amazon DynamoDB | Azure Cosmos DB | Cloud Firestore |
| 8 | A block storage service for use with virtual machines, offering persistent storage for data. | Amazon EBS | Azure Disk Storage | Persistent Disk |
| 9 | A managed container orchestration service based on Kubernetes. | Amazon EKS | Azure Kubernetes Service | Google Kubernetes Engine |
| 10 | A service for managing user access and encryption keys to secure cloud resources. | AWS Identity and Access Management (IAM) / KMS | Microsoft Entra ID / Key Vault | Cloud IAM / Cloud KMS |
| 11 | A platform that automates application deployment and scaling without needing to manage infrastructure. | AWS Elastic Beanstalk | Azure App Service | App Engine |
| 12 | A service that provides monitoring and logging of applications and infrastructure, offering insights into resource usage and performance. | Amazon CloudWatch | Azure Monitor | Cloud Monitoring & Logging |
| 13 | A domain name system (DNS) service that routes traffic globally and translates domain names to IP addresses. | Amazon Route 53 | Azure DNS | Cloud DNS |
| 14 | A load balancing service that distributes incoming network traffic across multiple targets, improving application availability. | Elastic Load Balancing | Azure Load Balancer | Cloud Load Balancing |
| 15 | A service that automatically scales your cloud infrastructure based on demand, ensuring resources are available as needed. | AWS Auto Scaling | Azure Autoscale | Compute Engine Autoscaler |
| 16 | A message queuing service that enables applications to send and receive messages between different components. | Amazon SQS | Azure Service Bus | Pub/Sub |
| 17 | A managed real-time data streaming service that collects and processes large amounts of data from various sources. | Amazon Kinesis | Azure Event Hubs | Pub/Sub |
| 18 | A fully managed, highly scalable data warehouse service optimized for analytics and large-scale queries. | Amazon Redshift | Azure Synapse Analytics | BigQuery |
| 19 | A service that automates the execution of workflows and allows the integration of different cloud services in a sequence of steps. | AWS Step Functions | Azure Logic Apps | Workflows |
| 20 | A service that integrates multiple data sources and enables data migration, transformation, and movement across platforms. | AWS Glue | Azure Data Factory | Cloud Data Fusion |
| 21 | A data catalog and governance service that helps manage metadata across your data estate, supporting compliance and security. | AWS Glue Data Catalog | Microsoft Purview | Dataplex |
| 22 | A set of machine learning and AI services that provide pre-built models, APIs, and tools for developers to easily implement AI in their apps. | AWS AI Services | Azure AI Services | Vertex AI |
| 23 | A service that allows you to define and deploy infrastructure using code, automating the management of cloud resources. | AWS CloudFormation | Azure Resource Manager (ARM) | Deployment Manager |
| 24 | A fully managed CI/CD service that automates the building, testing, and deployment of applications to production environments. | AWS CodePipeline | Azure Pipelines | Cloud Build |
| 25 | A desktop as a service (DaaS) offering that allows you to deploy virtual desktops in the cloud and access them remotely. | Amazon WorkSpaces | Azure Virtual Desktop | Workstations |
| 26 | A backup and disaster recovery service that helps to protect your data by creating backups and replicas of your cloud resources. | AWS Backup | Azure Backup & Site Recovery | Backup and DR Service |
| 27 | A service designed for big data analytics, allowing organizations to store, process, and analyze large datasets in real time. | Amazon EMR | Azure HDInsight | Dataproc |
| 28 | A file storage service for storing and sharing files with users, typically used in shared file systems across applications. | Amazon EFS | Azure Files | Filestore |
| 29 | A service that helps you transcode, process, and stream media content such as video and audio. | AWS Elemental MediaConvert | Azure Media Services | Transcoder API |
| 30 | A real-time communication service used for sending notifications, emails, and text messages to users and devices. | Amazon SNS / SES | Azure Communication Services | Firebase Cloud Messaging |

---

## **Summary Report**

### **Introduction**
This assignment compares and analyzes the similar cloud services offered by the three leading cloud providers—Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP). Each of these platforms provides a wide range of solutions covering areas such as computing, storage, networking, databases, analytics, and artificial intelligence. The goal is to identify the similarities and differences among these providers in terms of structure, naming, and unique capabilities, which give organizations multiple options for building and managing their cloud-based applications.

---

### **Similarities Between the Cloud Providers**
The three major cloud platforms have a similar foundation in the types of services they offer. Each one provides essential infrastructure and platform tools that support every major domain of cloud computing.

- **Compute:** AWS EC2, Azure Virtual Machines, and Google Compute Engine allow users to create and manage virtual servers that scale based on workload demands.  
- **Storage:** Services such as Amazon S3, Azure Blob Storage, and Google Cloud Storage are used for backups, static website hosting, and long-term data storage.  
- **Databases:** All three provide managed relational database options—AWS RDS, Azure Database Services, and Google Cloud SQL—supporting engines like MySQL and PostgreSQL.  
- **Serverless Computing:** AWS Lambda, Azure Functions, and Google Cloud Functions let developers run code without handling server management, reducing costs and complexity.  
- **Container Services:** Kubernetes-based services—EKS, AKS, and GKE—make it easy to deploy and scale containerized applications.  
- **Networking and Security:** AWS VPC, Azure Virtual Network, and Google VPC provide secure, isolated environments, while KMS, Key Vault, and Cloud KMS handle data encryption and key management.  
- **Monitoring:** AWS CloudWatch, Azure Monitor, and Google Cloud Monitoring track system performance, logs, and alerts to maintain reliable operation.  

These shared services demonstrate that the core components of cloud computing are almost identical across all three providers, even if their implementations differ slightly.

---

### **Key Differences and Unique Features**
Although all three platforms offer similar types of services, each has its own strengths:

- **Amazon Web Services (AWS):** Offers the broadest range of services and a global infrastructure. It’s known for scalability and flexibility, with key tools such as Amazon Redshift for analytics and AWS Lambda for serverless computing.  
- **Microsoft Azure:** Integrates smoothly with other Microsoft products such as Windows Server, Office 365, and Active Directory (now Microsoft Entra ID). It includes powerful data tools like Synapse Analytics and Data Factory and supports hybrid environments through Azure Arc.  
- **Google Cloud Platform (GCP):** Focuses on artificial intelligence, machine learning, and data analytics. Tools like BigQuery and Vertex AI make it ideal for data-driven solutions. GCP is also user-friendly and provides strong global networking capabilities.

---

### **Naming Conventions**
Each provider has its own naming style:

- **AWS** uses product-like names such as *Amazon S3*, *Elastic Beanstalk*, and *CloudFormation*.  
- **Azure** uses descriptive names that clearly describe their purpose, such as *Virtual Machines*, *App Service*, and *Storage Accounts*.  
- **GCP** keeps things simple with easy-to-understand names like *Compute Engine*, *Cloud Storage*, and *BigQuery*.

---

### **Conclusion**
In summary, AWS, Azure, and Google Cloud all offer a comprehensive set of cloud services that often overlap in purpose. They each cover core areas like computing, storage, and networking but differ in how they are designed and what they specialize in. **AWS** provides the widest range of options, **Azure** integrates best with Microsoft ecosystems, and **GCP** stands out in analytics and artificial intelligence.  
Understanding these similarities and differences helps users choose the right platform for their needs and enables organizations to effectively use multiple cloud providers in a unified strategy.

---


