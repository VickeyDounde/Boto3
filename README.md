# Boto3
by Vivek Dounde
How to Create a EC2 Instance?
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
###
    MaxCount=1, # Keep the max count to 1, unless you have a requirement to increase it
    InstanceType="t2.micro", # Change it as per your need, But use the Free tier one
    KeyName="ec2-key" # Change it to the name of the key you have.
    :return: Creates the EC2 instance.
###
