# Go App Setup

### Prerequisites

This service is designed and tested to be used on:
  - Ubuntu 14.04 LTS
  - Ansible 2.1.0.0

### Installation

You need ansible installed via apt-get or pip:

```sh
# apt-get install ansible
```
or

``` sh
# pip install ansible
```


### Configure

You have setup AWS Varibales in the following YAML file.

**roles/launch-instance/vars/main.yml**


``` 
ec2_access_key: xxxxxxxxxx
ec2_secret_key: xxxxxxxxxxxxxxxxxxxxx
region: us-east-1
project_name: Pro-go
instance_type: t2.micro
web_count: 1
app_count: 2
keypair: "{{ project_name }}-key"
security_group: "{{ project_name }}-SG"
image: ami-2d39803a 
```
### Run

To setup the Whole Stack Run Following command .
```sh
ansible-playbook go-env-setup.yml
```
### Testing
Open URL on Browser 
```sh
<URL_OF_Web_Server>
```

### Output
```sh
Hi there, I'm served from <Hostname of app server>
```