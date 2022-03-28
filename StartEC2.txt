
import boto3
region = 'us-east-1'
instances = ['i-01158f038ae1e1bd0']             #['i-0e2b9a8b4083245cb', 'i-031cab9a70f039788'] 
ec2 = boto3.client('ec2', region_name=region)

def lambda_handler(event, context):
    ec2.start_instances(InstanceIds=instances)
    print('started your instances: ' + str(instances))