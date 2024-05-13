# Boto3
by Vivek Dounde

Create a EC2 Instance using boto3
```
import boto3

def create_ec2_instance():

    try:
        print ("Creating EC2 instance")
        resource_ec2 = boto3.client("ec2")
        resource_ec2.run_instances(
            ImageId="ami-0f58b397bc5c1f2e8",
            MinCount=1,
            MaxCount=1,
            InstanceType="t2.micro",
            KeyName="vickey"
        )
    except Exception as e:
        print(e)

create_ec2_instance()
```
Things to Keep in Mind:-
MaxCount=1, # Keep the max count to 1, unless you have a requirement to increase it
InstanceType="t2.micro", # Change it as per your need, But use the Free tier one
KeyName="ec2-key" # Change it to the name of the key you have.
:return: Creates the EC2 instance.

Describe instance using Boto3

```
import boto3

def describe_ec2_instance():
    try:
        print ("Describing EC2 instance")
        resource_ec2 = boto3.client("ec2")
        print(resource_ec2.describe_instances()["Reservations"][0]["Instances"][0]["InstanceId"])
        return str(resource_ec2.describe_instances()["Reservations"][0]["Instances"][0]["InstanceId"])
    except Exception as e:
        print(e)
describe_ec2_instance()
```
Reboot Instance using Boto3
```
import boto3

def reboot_ec2_instance():
    try:
        print ("Reboot EC2 instance")
        instance_id = describe_ec2_instance()
        resource_ec2 = boto3.client("ec2")
        print(resource_ec2.reboot_instances(InstanceIds=[instance_id]))
    except Exception as e:
        print(e)
reboot_ec2_instance()
```
Stop Instance using Boto3
```
import boto3

def stop_ec2_instance():
    try:
        print ("Stop EC2 instance")
        instance_id = describe_ec2_instance()
        resource_ec2 = boto3.client("ec2")
        print(resource_ec2.stop_instances(InstanceIds=[instance_id]))
    except Exception as e:
        print(e)
stop_ec2_instance()
```
Start Instance using Boto3
```
import boto3

def start_ec2_instance():
    try:
        print ("Start EC2 instance")
        instance_id = describe_ec2_instance()
        resource_ec2 = boto3.client("ec2")
        print(resource_ec2.start_instances(InstanceIds=[instance_id]))
    except Exception as e:
        print(e)
start_ec2_instance()
```
Terminate Instance using Boto3
```
import boto3

def terminate_ec2_instance():
    try:
        print ("Terminate EC2 instance")
        instance_id = describe_ec2_instance()
        resource_ec2 = boto3.client("ec2")
        print(resource_ec2.terminate_instances(InstanceIds=[instance_id]))
    except Exception as e:
        print(e)
terminate_ec2_instance()
```
