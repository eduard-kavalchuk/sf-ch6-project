Before running playbook:
1. Create a user named "user1" on a local system and generate its ssh keys.
2. Use provided Terraform files to create a necessary infrastructure and specify external IP addresses on created VMs in inventory.ini file.


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

Default data directory of postgres (https://www.digitalocean.com/community/tutorials/how-to-move-a-postgresql-data-directory-to-a-new-location-on-ubuntu-22-04):
```
/var/lib/postgresql/14/main
```

scp ed@51.250.92.94:/etc/postgresql/14/main/postgresql.conf .

/usr/lib/postgresql/14/bin/initdb --encoding=UTF8 --pgdata=/mydata/pgdbdata/

/usr/lib/postgresql/14/bin/initdb --encoding=UTF8 --pgdata=ed/pgdbdata/

sudo chmod a+w /var/run/postgresql


Find a current data directory:
1. sudo -u postgres psql
2. SHOW data_directory;
3. \q

sudo service postgresql stop
sudo rsync -av /var/lib/postgresql   /mnt/pgdata/
sudo mv /var/lib/postgresql/14/main /var/lib/postgresql_backup
sudo vi /etc/postgresql/14/main/postgresql.conf
Change to:
data_directory = '/mnt/pgdata/postgresql/14/main'
sudo service postgresql start
