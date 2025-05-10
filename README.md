AWS RDS Instance Scanner

A Python tool to retrieve metadata of all AWS RDS instances in a specified AWS region. The tool outputs the metadata in JSON format, including Engine Type, Status, and Endpoint Address.

Prerequisites
Python 3.8 or higher
AWS CLI configured with appropriate credentials
IAM permissions for rds:DescribeDBInstances (e.g., AmazonRDSReadOnlyAccess policy)
Git installed

Setup

Clone the Repository:
git clone https://github.com/your-username/aws-rds-scanner.git

cd aws-rds-scanner


Create a Virtual Environment:

python3 -m venv venv

source venv/bin/activate  # On Windows: venv\Scripts\activate


Install Dependencies:

pip install -r requirements.txt


Configure AWS Credentials:

Run aws configure and provide your AWS Access Key ID, Secret Access Key, and default region.



Usage

Run the script with the --region argument to specify the AWS region:

python3 rds_scanner.py --region us-east-1

Example Output


[ 
  
    {
        "DBInstanceIdentifier": "test-db",
        
        "Engine": "mysql",
        
        "Status": "backing-up",
        
        "Endpoint": "test-db.cbsmo6q4mt6x.ap-south-1.rds.amazonaws.com"
    }
]




Troubleshooting

Invalid Region: Ensure the region is valid (e.g., us-east-1, eu-west-1).

Permission Denied: Verify your IAM user has rds:DescribeDBInstances permissions.

Empty Output: If no RDS instances exist in the region, an empty array [] is returned.

License
MIT License
