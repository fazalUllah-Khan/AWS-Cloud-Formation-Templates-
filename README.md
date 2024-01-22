# AWS-CloudFormation-Templates-
What is Iac, AWS CloudFormation, and some useful templates of Cloud Formattions

# What is IaC ?
Infrastructure as code (IaC) is a powerful and mature technology used by DevOps teams to automate resource provisioning on the cloud. The basic idea of IaC is that you can maintain a simple, human readable configuration file, called a “template”, defining a complex infrastructure.

Amazon provides its own IaC platform called CloudFormation. This is not the only option for IaC on Amazon - you can also use third party automation platforms like Terraform, Puppet, and Chef.

# What is AWS CloudFormation?
AWS CloudFormation is a solution that facilitates modelling and setting up AWS resources, which helps you save time on management. CloudFormation provisions and configures resources based on a template you create, which specifies the resources you require (such as EC2 instances or RDS DB instances). There is no need to create or configure each resource individually.

The template you use in CloudFormation template will be a text file in JSON or YAML format. The file can be saved with various extensions (e.g. .json, .yaml, .txt or .template). You should choose the format that is most comfortable for you to work with. Consider, for instance, that some features available in YAML cannot be found in JSON.

# How Does CloudFormation Work?
Here are three fundamental CloudFormation concepts you should know about:
	Template—a JSON or YAML file that lets you define AWS resources declaratively. CloudFoundation uses templates as a blueprint when automatically configuring and deploying resources.
	Stack—a deployed template creates resources as a “stack”. When you update or delete resources the changes are applied to the entire stack.
	Change Set—you can run updates on your stack and then CloudFormation handles the changes. Change Sets can help you see the impact of these changes before the update is applied.
AWS CloudFormation makes service calls to AWS to provision resources and configure them. This occurs when a stack is created. However, CloudFormation is restricted to performing actions for which you have permissions.

# How the process works:
Use AWS CloudFormation Designer (or other text editor) to modify an existing CloudFormation template or create a new one. Alternatively, use a ready-made AWS template.
Save the template—you can save it in an S3 bucket or locally.
Specify the template file’s location to create a CloudFormation stack. For example, you can define paths on local computers or provide Amazon S3 URLs. Templates that contain parameters allow you to specify input values when you create a stack. These parameters can help users customize the resources they create.
To create stacks, you can use the AWS APIs, CLI or the CloudFormation console.
        Once your resources are set up, CloudFormation reports that the stack was created. At this stage, you can start using any resources in the stack. If the process of creating a stack fails, CloudFormation will undo your changes by deleting all resources it created.

# AWS CloudFormation Template Components
AWS CloudFormation templates contain nine main objects:
	Format version—defines the version of the template format (currently only one option, 2010-09-09)
	Description—let you specify comments about the template.
	Metadata—let you use JSON or YAML objects to add information.
	Parameters—let you customize your template by adding or modifying custom values, before deployment and at runtime.
	Mappings—let you map keys to corresponding named values, which you specify in conditional parameters. To retrieve values from a map, you can use the Fn:: FindInMap intrinsic function.
	Conditions—define the resources that are created and when their properties are assigned to values. This can happen during updates or stack creation.
	Transform—builds an easy-to-use declarative language for CloudFormation and let you reuse template components. Each template lets you declare a single or multiple transforms.
	Resources—let you declare which resources—such as S3 buckets or EC2 instances—should be used for the stack.
	Output—describes the output values allowed to be imported into other stacks or values that should be returned when you view stack properties.

# What is AWS CloudFormation Designer?
CloudFormation Designer offers graphic functionality that helps you create, view, and modify CloudFormation templates. Designer let you diagram template resources via a drag-and-drop interface. You can edit these details through an integrated YAML and JSON editor. Designer is highly useful for quickly finding interrelationship between the resources of a template and easily modifying the template.
# Visualize Template Resources
It can be difficult to parse JSON or YAML text files to see all resources inside the template and the relationships between them. Designers can help you visualize these aspects, so you can better understand these processes. You can use it to:
View a graphic representation of AWS resources specified in the template and their relationships
View metadata-based diagrams. Designer saves changes in metadata, ensuring you see the most recent updates.
# Simplify Template Authoring
When authoring template resources, you need to manually edit YAML or JSON files. This is an error-prone and tedious process. Instead, you can use Designer’s drag and drop interface to add new resources to a template, and drag connections to establish relationships. The tool automatically makes the relevant changes to the JSON or YAML files. Additionally, when you create a new template, Designer adds basic relationships that ensure you create a valid template.
Simplify Editing with the Integrated YAML and JSON Editor
The integrated editor enables you to make all template modifications from within the AWS CloudFormation console. You don’t have to use different text editors to change or save different templates. Additionally, the integrated editor offers an auto-complete functionality that lists all properties per resource, to ensure you don’t have to memorize or search for them. The integrated editor can also convert YAML templates to JSON and vice versa.

# AWS CloudFormation Template Examples
     AWS provides a wide range of pre-built templates, which you can use directly to automate actions on AWS, or customize to create your own automation.

# Auto Scaling
The following templates provide policies for creating an Auto Scaling group:
o	Load-based auto scaling—uses scaling policies based on CPU usage to launch and stop EC2 instances across various Availability Zones. It provides email notifications of scaling events.
o	Auto scaling with update policies—incorporates an update policy to keep two instances running when an update occurs.
o	Scheduled auto scaling—uses schedules to adjust the number of EC2 instances in the scaling group at specified times.

# Amazon Services
The following templates create AWS services:
o	Instances in an EC2 security group—creates Amazon EC2 instances within an EC2 security group.
o	Amazon S3 bucket—creates an Amazon S3 bucket that is publicly accessible through websites. Provides a deletion policy that ensures the bucket is retained when you delete the stack.
o	Automated deployment of Video on Demand—launches Video on Demand with all related components, including (by default) Lambda, S3 buckets, Step Functions, Elemental MediaConvert, DynamoDB and more. The template is customizable, so you can add features, for example leverage video APIs like Cloudinary or IBM Watson.
o	Hello World AWS Batch—creates a Batch computing environment with a job queue and definition for a Hello World batch job. The job definition can be modified to run other batch scripts or Docker containers. Batches run on low-cost AWS spot instances.
o	DocumentDB Cluster—creates Amazon DocumentDB clusters with primary instances.
o	Lambda security group—uses AWS Lambda functions and customized resources to add security groups to an existing security group list. This allows you to dynamically build a list that includes both existing and new groups.
# Security
The following templates use security policies to create and configure resources:
o	Identity Access Management (IAM)—use various policies to create multiple AWS IAM groups and users.
o	Simple Notification Service (SNS)—creates Amazon SNS topics for sending messages to IAM users and Amazon SQS queues (two of each). One user has published access while the other has read access to view the messages.
o	Amazon SQS queues with CloudWatch—creates SQS queues with alarms from CloudWatch to help you monitor the depth of your queues.
o	AWS Config rules and delivery channel—launches an EC2 volume with AWS Config rules to ensure that all volumes have the necessary taga. Enables automatic I/O.

