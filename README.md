Installation Procedures:

1. clone or download this repo and `cd` to `ansible-vagrant-elkstack` folder.

2. Install the necessary Ansible roles by running : `ansible-galaxy install -r requirements.yml`.

3. Then just `vagrant up` .

4. Go to :

	`http://172.28.128.30`  for `elkstack`
	`http://172.28.128.31`  for `application server`

5. add in `/etc/hosts` file these line to set elkstack as hostname for local use
	
	`172.28.128.31 elkstack`

Thanks to @`bastly` for ansible roles.
