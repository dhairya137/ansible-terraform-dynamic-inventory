## Dynamic Ansible Inventory file

**We are using ansible aws plugin to use dynamic inventory.**

<hr>

1. inventory_aws_ec2.yml this is config file for our hosts.

2. run this command to get all your running ec2 instances.

```bash
 ansible-inventory -i inventory_aws_ec2.yaml --list
```

3. Create aws ec2 instances with terraform.
4. Follow this commands. This will create 3 ec2 instances.

```bash
terraform init
terraform apply --auto-approve
```

5. Execute ansible playbook on this new created ec2 instances.

```bash
ansible-playbook -i inventory_aws_ec2.yaml install-docker.yaml
```

6. Now when you create new ec2 instance with terraform then just follow the above command and it will install the docker.
