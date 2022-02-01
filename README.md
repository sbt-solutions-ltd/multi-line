## About

GitHub action to process environment variables based on GitHub branch and Terraform environment.
This action was intended to work with AWS cloud.

## Usage

The action was created to pass variables based on the branch you are pushing your code in. And for it to work, the following 
variables need to be provided:
```
          SSH-KEY-DEV:     SSH key for your EC2s in your development environment.
          SSH-KEY-TEST:    SSH key for your EC2s in your testing environment.
          SSH-KEY-PROD:    SSH key for your EC2s in your production environment.
```

In addition, the action could process the following variables as well:

```
          BASTION-IP-DEV:                IP of your AWS Bastion host in your development environment.
          BASTION-IP-TEST:               IP of your AWS Bastion host in your testing environment.
          BASTION-IP-PROD:               IP of your AWS Bastion host in your production environment.
          SG-ID-DEV:                     Security group ID of your Bastion SSH development sg group.
          SG-ID-TEST:                    Security group ID of your Bastion SSH testing sg group.
          SG-ID-PROD:                    Security group ID of your Bastion SSH production sg group.
          REGION-DEV:                    The region for the development resources.
          REGION-TEST:                   The region for the testing resources.
          REGION-PROD:                   The region for the production resources.
          SG-SCRIPT-URL-DEV:             The URL of the dev casino SG
          SG-SCRIPT-URL-TEST:            The URL of the testing casino SG
          SG-SCRIPT-URL-PROD:            The URL of the production casino SG
          AWS-BUCKET-KYC-DEV:            The S3 bucket KYC dev
          AWS-BUCKET-KYC-TEST:           The S3 bucket KYC testing
          AWS-BUCKET-KYC-PROD:           The S3 bucket KYC production
          S3-BUCKET-DEV:                 The S3 bucket Strapi dev
          S3-BUCKET-TEST:                The S3 bucket Strapi testing
          S3-BUCKET-PROD:                The S3 bucket Strapi production
          DB-ADDR-DEV:                   The DB dev address
          DB-ADDR-TEST:                  The DB testing address
          DB-ADDR-PROD:                  The DB production address
          SOFTSWISS-MP-REST-URL-DEV:     The Softswiss dev address
          SOFTSWISS-MP-REST-URL-TEST:    The Softswiss testing address
          SOFTSWISS-MP-REST-URL-PROD:    The Softswiss production address
          KAFKA-BOOTSTRAP-SERVERS-DEV:   The DB dev address
          KAFKA-BOOTSTRAP-SERVERS-TEST:  The DB testing address
          KAFKA-BOOTSTRAP-SERVERS-PROD:  The DB production address
```

## Output

As a result, the action will return the following outputs:

```
         SSH-KEY-SINGLE:          "EC2 SSH key"
         ENV_BRANCH:              "The branch tag to be applied"
         ENV_REGION:              "The region to create the resources in"
         BASTION_IP:              "The IP of the Bastion host"
         SG_ID:                   "The ID of the Bastion host SSH security group"
         KAFKA-BOOTSTRAP-SERVERS: "The DB production address"
         SOFTSWISS-MP-REST-URL:   "The Softswiss address"
         DB-ADDR:                 "The DB address"
         S3-BUCKET:               "The S3 bucket for Strapi"
         AWS-BUCKET-KYC:          "The S3 KYC bucket"
         SG-SCRIPT-URL:           "The URL of the casino SG"
```

## Example

For more information , please refer to the example provided in the repo - github_action_example.yml