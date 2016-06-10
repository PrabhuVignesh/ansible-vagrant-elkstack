Installation Procedures:

1. Install the necessary Ansible roles by running : `ansible-galaxy install -r requirements.yml`.

2. clone or download this repo and `cd` to gitlab folder.

3. Then just `vagrant up` .

4. Go to :

	`http://192.168.9.90`  for `elkstack`
	`http://192.168.9.91`  for `application server`

5. add in `/etc/hosts` file these line to set elkstack as hostname for local use
	
	`172.28.128.31 elkstack`

Thanks to @`bastly` for ansible roles.