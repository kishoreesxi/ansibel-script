
###################################
## Deploy Neo4j CC Using Ansible ##
###################################

Step 1: Update the contents of inv-cluster to match your deployment configuration with
a) appropriate number of core servers
b) appropriate number of read replica servers
c) associated IP addresses of all servers

Step 2: Run the following to prepare the target servers for installation: 
$ ansible-playbook -i inv-cluster -u <REMOTE_USER> sysprep.yml

Step 3: Install and configure Neo4j:
$ ansible-playbook -i inv-cluster -u <REMOTE_USER> neo4j-install-tar.yml
$ ansible-playbook -i inv-cluster -u <REMOTE_USER> neo4j-config-tar-cluster.yml

Step 4: Start and Stop Neo4j
$ ansible-playbook -i inv-cluster -u <REMOTE_USER> neo4j-start-services.yml
$ ansible-playbook -i inv-cluster -u <REMOTE_USER> neo4j-stop-services.yml
