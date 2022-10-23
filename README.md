Before running this playbook use provided Terraform files to create a necessary infrastructure and specify external IP addresses on created VMs in inventory.ini file.  
Run playbook (with a verbose output) with specified inventory and groups:
```
ansible-playbook -i hosts -l <groups> <file> -vv
```
Check a yaml file with linters:
```
ansible-playbook --syntax-check <file>
```

Format all terraform files in a directory and nested directories:
```
terraform fmt
```
Check a terraform file with linters:
```
tflint <file.tf>
```
Follow this link to change default data directory of postgresql:
https://www.digitalocean.com/community/tutorials/how-to-move-a-postgresql-data-directory-to-a-new-location-on-ubuntu-22-04
