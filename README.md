# Testing CI Pipeline using Jenkins 

A simple Python application that provisions an AWS EC2 environment resources and configures a web server leveraging CI pipeline tools and deployment tools.

## Getting Started

This mini project was developed using the AWS SDK for Python called Boto3. The approach was implemented using available services for EC2. See [Boto 3 Documentation](https://boto3.readthedocs.io/en/latest/) for reference.

### Installs

Install AWS CLI and Boto3 via command line

```sh
    $ pip install awscli boto3
```  

To configure the AWS CLI 

```sh
    $ aws configure
```

## Usage

This application automatically connects to AWS to provision an EC2 instance on a pre-defined user account. Set up an authentication credentials with a programmatic access and right permission to access Amazon EC2 services.

### Requirements

All configuration information as listed in files 'setup.cfg' and 'user-data.txt' needs to be available and configured. These files are used to define profile information and properties for environment and web server.


### Running the script

To use this script: run program 'provision_ec2_env.py'
This is the main function to provision your EC2 instance.

```sh
    $ python provision_ec2_env.py
```

To clean up 

```sh
    $ python provision_ec2_env.py -t
```

Add configuration file with the following sample information:

``` [setup]
zone = us-east-2a
min_count = 1
max_count = 1
image_id = ami-25615740
instance_type = t2.micro
key_name = test-3-18
securitygroup_id = sg-8ff98ee4
user_data = user-data.txt
```

## Testing

An Integration Testing technique was adopted using Python Unit Testing framework.

### Approach

An automated approach was implemented focusing on two scenarios with full independency with a SetUp and TearDown methods:

    1. Test Instance Creation
    2. Test web server and homepage display

see file 'scenarios' for details

### Integration-Testing

To test: run program 'test-scenarios.py'

```sh
    $ python test-scenarios.py
```

Ensure to test program each time you make changes to main function. In this case "provision_ec2_env.py"
