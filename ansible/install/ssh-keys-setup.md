## create a user on all machines ( controller & all targets )

        sudo wget https://raw.githubusercontent.com/lerndevops/labs/master/scripts/setupUser.sh -P /tmp
	sudo bash /tmp/setupUser.sh
	
	Note: above script will setup username & password as below 
	
	USERNAME: devops
	PASSWORD: today@1234
	
	cd /tmp ; git clone https://github.com/vsravuri/vr_devops_labs
	cd /tmp/vr_devops_labs/cloud
	bash setupsshuserjenkins.sh
	

### genereate ssh keys for above user on contrller machine 

```
1) switch to user ( su - devops )
2) run "ssh-keygen" command as user ( this will genereate ssh keys for the user ) 

validate:
     
  cd /home/devops/.ssh 
  cat id_rsa.pub 
```
### copy user ssh keys from ansible contrller to all target hosts

```
On Ansible Contoller:
	
  swith to the user OR be as devops user ( su - devops )
  
  ssh-copy-id devops@target1ip -- hit enter -- enter the password of target server when it prompted 
  ssh-copy-id devops@target2ip -- hit enter -- enter the password of target server when it prompted
  .
  .
  .
  .
  ssh-copy-id devops@targetnip -- hit enter -- enter the password of target server when it prompted

```	
	

