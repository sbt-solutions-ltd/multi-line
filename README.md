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
          BASTION-IP-DEV:  IP of your AWS Bastion host in your development environment.
          BASTION-IP-TEST: IP of your AWS Bastion host in your testing environment.
          BASTION-IP-PROD: IP of your AWS Bastion host in your production environment.
          SG-ID-DEV:       Security group ID of your Bastion SSH development sg group.
          SG-ID-TEST:      Security group ID of your Bastion SSH testing sg group.
          SG-ID-PROD:      Security group ID of your Bastion SSH production sg group.
          REGION-DEV:      The region for the development resources.
          REGION-TEST:     The region for the testing resources.
          REGION-PROD:     The region for the production resources.
```

## Output

As a result, the action will return the following outputs:

```
         SSH-KEY-SINGLE: "EC2 SSH key"
         ENV_BRANCH:     "The branch tag to be applied"
         ENV_REGION:     "The region to create the resources in"
         BASTION_IP:     "The IP of the Bastion host"
         SG_ID:          "The ID of the Bastion host SSH security group"
```

## Example

For more information , please refer to the example provided in the repo - github_action_example.yml